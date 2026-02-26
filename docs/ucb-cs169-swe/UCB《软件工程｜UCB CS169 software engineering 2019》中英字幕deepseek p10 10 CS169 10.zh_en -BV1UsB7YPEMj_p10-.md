# UCB《软件工程｜UCB CS169 software engineering 2019》中英字幕deepseek p10 10 CS169 10.zh_en -BV1UsB7YPEMj_p10-

🤧咳。

![](img/efdf1bf07734ddf3689d6364b4d2b742_1.png)

All right， so people are still coming in but。That should actually say lecture 2。 But regardless。

 micro quiz。 So it's micro quiz 3 on grade scope。 So if you just open up grade scopepe。

 it should already be active。 but a few short questions。And then。You know。

Take the microquiz and then in about 10 or 15 minutes we will get started with lecture content。

 so as a reminder， no additional resources for the microquiz， but of course。

 whatever you need to take the microquiz， have that out and then when you're done just wait。



![](img/efdf1bf07734ddf3689d6364b4d2b742_3.png)

IX应。认会下。

![](img/efdf1bf07734ddf3689d6364b4d2b742_5.png)

嗯。All right， so take about five more minutes for the microquiz if you're still working on it and it will close at 955。

不要。耳机啊。可以啊。All right，So it is 955 so that the quiz should have closed。诶。

And let's see we got 70 submissions。A little bit of a drop off。

 There's also not 70 people in the room。 So we will be working on improving that in the future。

Actually， let's not plug in the projector with grades showing that would be a terrible idea。

In lecture right。Yeah， well， I'll do some stuff。I mean， it's， you know， it's just grade scopepe。

 So if you're willing to wake up at 9，30 and take a quiz in bed。

 then it is possible to take the micro quiz at home。 I mean， I was a student， too。

 So I know all the rules and how to get around things。



![](img/efdf1bf07734ddf3689d6364b4d2b742_7.png)

You know， as long as I mean， the point is to not be cheating is really what I mostly care about。 And。

 you know， with the micro quizzes， the point is also that like frequent quizzing helps you as students。

 they are not again， meant to be a significant part of your grade but they are meant to help you keep up with the material。

 and theyre also a good way to give you a reminder if they are tricky concepts or things like that。

 so。With that， today's lecture is a continuation of the stuff that is sort of finishing up the human factor side of the project。

 So we'll talk today about story points， velocity， putting stuff in pivotal tracker then we'll go about some really cool testing tools called cucumber and Cappibarra And so these will be ways of turning the feedback and story ideas that you get from your customer into actionable test cases that you can run。

 So for those of you who have legacy projects， you will actually see your past colleagues。

 work in that they have written all these test cases。

 and so you can read through the specifications and actually get a sense of what your application should do from a human level and then。

😊，On the note of projects。The voting form for projects will open tonight。

 So we're kind of gonna bin things。 So every like six hours。

 it's gonna be a roughly randomized group of first come first serve。

 So you don't have to get there like read at 6。 but or five or whenever it actually opens tonight。

 But within a we kind of bin people by Vrs and tie break randomly。

 But you'll have project voting tonight So what you'll do is there'll be a Google form。

 you just rank your projects one through 18 or so。 for those of you who brought in a specific project barring anything heinously weird。

 you will get your project choice since you brought it into the class。

 And then everyone else will be you know we do rank choice voting with that。 So early next week。

 you should know what project you're going to be working on。

 we will pass along customer contact information。 So next week。

 we will expect you to send an introduction to your customers set up a meeting And if any of you have problems getting in touch with your customers。

We will sort of help you along in that regard。And just because it's worth clarifying today's lecture will be content for the midterm。

 some of the cucumber and Kay bar stuff you will have hopefully seen in homework4。嗯。And， you know。

 just。As a reminder， because it's new content， it won't not be as emphasized。

 but everything up until the end of this week will be fair game for the midterm next week。

 And I released some examples on Piazza。 So you have a question bank。

 You have half of two different past midterm。 So there's a half that's multiple choice and a half that's open ended。

 This semester's midterm will follow a roughly similar breakdown。

 there will be about half multiple choice and half a little bit more open endeded and each of those halves will comprise all of lecture content。

 So there will be multiple choice questions on Ruby。

 and there'll be open ended questions on Ruby and so on。 So with that。😊，Assuming my map cooperates。

 we're gonna talk about points and velocity。 So the goal of story pointing。

 So we talked about we have stories。 we're gonna turn those into tests。

 The goal of story pointing is to give us an estimation of sort of productivity。

 They help you as a team gauge how much work you can accomplish in a two week iteration。

 They also help you structure your conversations with a customer as to how much work you can tell them you can accomplish and it prevents you hopefully from overcommiing。

 It also gives you a sense of learning how to estimate how much work you will be doing as a team。

 So estimation is notoriously difficult。 It is something that you will all need to practice that。

 It is something that teams。😊，All the time struggle with。

 but it is something that you continually improve on。You know， if。If you don't do any estimation。

 it becomes very difficult then to say， you know how long will this take， how many， you know。

 how much kind deliver for a customer if you're running a consultancy， So pivotal labs。

 the makers of pivotal tracker tracker is primarily design and development consultancy So they build software for other people。

 if you don't have a good way of estimating how can you possibly build a customer for the work that you're doing。

 right， you don't end up knowing until it's done， how long it would take And so for a customer。

 that's hard to say， you know， how much they could commit in terms of a budget。And basically。

 the idea here is that we're going to take each of our stories and break as we break them down。

 estimate how much time we expect them to。You know。

 our how much time we expect them to take to deliver。 So our goal here is not to say that， like。

 you know， we're gonna to get a story that says users can log in through Facebook。

 We don't necessarily always want to say we can deliver。 We can guarantee delivery by this date。

 because。If you've heard the phrase unknown unknowns。

 every design and development story has these unknown un nutss。

 We don't know what might come up in the development of this story， especially for， you know。

 you all who are， you know， up and coming software engineers， you don't know。

 especially what you don't know， right。And so you don't necessarily want to say。

 like we can 100% get this done by X， Y Z dates。 But you do want to say that I'm going to work with you to figure out how much we can get done by this time and story pointing will be a tool in that way。

 So the way that pivotal usually does this with their clients is they start with a series of very high level but shorter meetings。

 So， you know， here are our goals for this project。 then they bring in engineers。

 So as an engineer who has built similar products before。

 I now have a more detailed understanding of how this might work。And then with you know， engineers。

 you help identify the things that you understand。 So if it's a rails app with a login flow， well。

 that is a relatively constrained process。 I've mentioned the gem omnioff before once or twice in lecture。

 you have a tool that you know how to use you can tell a customer， hey， we've done this before。

 this is something that we understand is a smaller medium story。 And we can deliver this in。

 you know， similar type of time frame。 And then the goal is， you know。

 when you have uncertainty to be able to document that more clearly and say， hey。

 what we're doing here is some kind of， I don't know， document processing， machine learning。

 you know， any other type of work that may be more unknown and you can communicate that with a customer。

 And so。You know， but as you go through this， you go from less detail to a little bit more detail。

 And the goal is to estimate the cost。 So in the professional world， this is called a bid， you know。

 how much money， how much total time do we think this feature or project will be。

And then the goal is to then estimate what we call points。For this class， we're using points。

A common thing that you will also say in industry is sometimes referred to as t-shirt sizing。

 so t-s shirtt sizing， extra small， small， medium large， those kinds of things。 But you know。

 basically any of these methods， the goal is to have a scale and for the course of your project。

 you stick to that scale now。These points are arbitrary values。 They have no units。

 So for this course， we're going to recommend that you do something relatively simple，1，2，4，8。

 You will notice that 3，5，6，7， Yeah， are all missing。

 And the reason for that is similar to t-shir sizes。

 you will not have the ability to give a very good estimate， especially at the beginning。

 But what you will be able to say is that a one point story is。

Usually we' say about half a day's worth of work if you're just able to sit down coding。 So you know。

 three to four hours of dedicated coding time， a two point story is roughly you know a full dedicated day of coding time。

 So for you as students， you're probably not going to dedicate 8 straight hours of coding。

 although you're more than welcome to do that， you know you get into a good flow。

 but you know if you have a two point story， that will be something that you will implement over the course of a few smaller work sessions。

 probably and they kind of double out from there with the idea that the larger stories。

 we just really have no idea try most companies try to avoid anything much larger than in this case。

 eight point stories with the idea that things that are big should be broken down。

 and we'll talk about that in a second。 So other methods that are commonly used or the Fibonacci sequence obviously you don't repeat 1。

 but you know1，3，5，8 occasionally teams will use 13。 But you each of these。

The goal is that within a team， you have a set of points。

 and the very upper limit of your point scale is going to be very rare。 These are things that。

 you know， if in this class， we're gonna recommend 1，2，4，8。

8 points for you should be pretty rare as a story。 that's gonna to be a sign that you should break this story up into multiple iterations。

You know， for teams that use tshir sizes， they might say large and extra larges are very rare。

 and those should be broken up。 If you soacci numbers， it might be 8。 It might be 13。

 Whatever your scale for a team is is going to be， you know， up to that team。 And so。

For you all and your project teams， you're going to have to figure out exactly how you feel together and we'll talk about the best way to do that。

All rightSo。What we call stories that are too large and get split up are epics。

 So epics are a collection of smaller stories that together deliver a single shared feature。 So。

 you know， if we。Have， let's see。 if we have some story about user login， maybe the， you know。

 the the story is users can log in from any third party authentication service。 So Google， Facebook。

 Twitter， Gitthub， whatever。 If that's one story and you have a list of services。

 you might start that off as an eight point story。 and then break that down into smaller stories that you each classify in terms of an epic。

 And so an epic is really saying that I have this feature from a customer。

That is too big to deliver in one step， so I'm going to break it down and deliver in smaller steps。

So we have a measure called velocity。 It is a rate。 So like physics velocity is a rate。

 The average number of points you can say per week， we could do per iteration。 you know。

 it is a points per time。 So in this case。 And the goal here with velocity is not necessarily to say。

 you know， we're gonna， we're not going to be measuring your projects by some arbitrary measure of velocity。

 What we are saying， though， is everyone within a team should try and work towards within a team having a consistent velocity。

 So。😊，Points are an arbitrary value。 So within your team of 6。

 you should be agreeing to try and work towards figuring out how much one point should be。

 And I'm gonna tell you to roughly start off as 3 to 4 hours of dedicated coding time is going be roughly one point。

 So how do you do this as a team。Well， one way to do this is make sure that everyone as your team is going to be at this meeting。

 So if everyone is involved， everyone should be there and。What we recommend is that。

You have one person who is sort of leading these meetings。 So this role is called the product owner。

 This is a specific role in agile software development。For each iteration。

 one person on your team will be the product owner。

 You can swap that out per week if you want to give everyone a chance。 But， you know， you'll have。

 you'll rotate that rollout to the course of this class。

 And so the product owner is gonna be the one who is leading this meeting who is representing the voice of the customer。

 So your customer won't be here for this meeting because it's。

knowIt's about taking the features of the customer asked for and translating them into technical details。

 but you're each going to go one story at a time。Independently of others。

 So when we first vote for clicker questions， we tell you not to talk to your peers。

 The idea is to get you to think first。 story pointing works in a similar way。 You each read a story。

 You will each say， I think this will be 1，2，4，8 points。 And then together， you will come and say。

 okay， here are the points that we have as a team。You， I think it's one point。

My colleague thinks it's two points。 Maybe someone thinks it's four points。

 and we have a really wide range。 What you should then do is talk about it and say， okay。

 after talking about it， here are our revised estimates。

 And the important thing here is that if you have a range of estimates。

 pick the high value and not the average。 So， you know。

 usually someone who thinks that a story is going take longer has an inclination that maybe their teammates don't maybe they're saying I'm going be the one implementing the story。

 I'm a little bit newer at this。 And I know it's gonna to take me longer。 And that's perfectly okay。

 You know， as you are new， especially your first iteration or two。😊，You know。

 you will want make sure that you're allocating a little bit of extra time because you don't know everything that you don't even know yet。

 right， You can't necessarily know the hurdles that you run into until you've actually set up and installed your project's dependencies。

 You don't know that you might run into an issue or something like that so。You know。

 just keep them mind。 And again， diversity in people's views for story points is going to happen。

 It's a common scenario。 So remember that you're all working together to deliver。

 a project to the customer。 If someone says it's one point and someone says it's 8 points。

You clearly have different expectations。 So talk about why those expectations are different。

 What is someone， you know， saying that this story is going to take a really long time， you know。

 forgetting in here。 What are you， if you say that a story is gonna be small。

 What might you be leaving out in expecting a story to be small when you your teammate thinks it's larger and all those as initial guesses。

You know， if you're putting good faith into this， those are all reasonable estimates。 So， you know。

 don't don't call out your peers if they think that something is going to be way easier or way more difficult than than you think。

 And similarly， don't think of it as an indictment of ability。 It's， you know。

 a difference in sort of perspective on you know， ideas that you may or might not be skipping。

 But so work on this as a team。 And it sounds easy。

 but I can promise you that software project estimation is one of the more challenging things。

That people do so。So， you know， if you， again， if you have a set of stories that are greater than in this case。

 four points， those related stories should be broken down and put together in an epic。

 So they are things that deliver a single larger feature and Pial tracker will have tools to actually group these stories together。

嗯。😊，And again， sort of what I said， it doesn't matter exactly what your velocity is overall。

 We're not going to be measuring this or setting a goal。

 What we do want to have happen is for your teams to approach consistency in the number of points that you deliver per iteration。

 So if your teams， you know， is。Starting off by saying， you know。

 we're each going do pair programming。 So we have three stories at a time for six people。

 These are each two point stories。 You， we're gonna deliver six points per iteration。

 We're gonna to deliver eight points per iteration， something like that。

 If the goal will then be to sort of keep up that pace。

 If you start off delivering six points per iteration and then you go up to8。 know。

 that's not a bad thing， especially if it means that you're getting just faster in learning。 know。

 that's okay。 you really don't want it to trend down unless you happen to realize that like our first iteration。

 we overcommitted and we just overworked ourselves。 You。

 there are reasonable reasons why things will change， but you should approach consistency over time。

 and just always ask yourself at the end of delivering a story。

 Was this really a two point story or should I have revise that maybe it was easier than I thought And I thought this thing was gonna to be two points。

 but I knocked it out in one sitting and that was great。

 So now I have a better sense of what's easy and what's hard。But just have that self reflection。

How do you know if a story needs to be broken down？

Usually what we do is we have this term called a spike。

 And so a spike happens when you say I have a series of stories， I have a feature。

 I just don't know what I don't know yet。 And so the goal with a spike is to say I'm going to take a dedicated amount of time in a typical world if it's a large story。

 This will be about a day's worth of work， but you're going to say I'm going to hammer out a very basic prototype that is incredibly hacky。

 I'm going to do a little bit of research。 I'm going to you figure out the unknowns。😊。

And then at the end of it， I'm going to throw that code away and throw that code away is the important part。

 because what it allows you to do is dedicate a time box。

 a amount of time that says I can just experiment。 come back with more information。

 This is not production quality code。 It's not stuff that's necessarily going to be tested。

 But what it is is allocating time for research。 And then when you come away with that spike。

 you will have a better sense of how to how to break down a specific story。 So。You know。

 that is a spike is a technical term。 and if you see yourself having four or eight point stories。

 you should think about， you know， how to， how to break those down。

 how to dedicate time to some experimentation and research and so。

That is a quick overview of story pointss。 You're going to be expected to do this for each iteration as you plan how much work you're going to do。

 and so you know， just you'll have a few opportunities start this course to get practice with that questions on story pointss or anything so far。

Cool， soe， first clicker question of the day。S it open。 It is open。

 So for the last three team iterations， the velocity was 8。

 and the team blues velocity was 8 and team goal was 4， which， if any。

Information can we gain by these two different team velocities。哦。

LetsSee if we can get a few more votes in in the last 10 seconds or so。Cool， so turn that off。

 we have a pretty good distribution of responses。A couple E's。

 So we'll talk about that this at the end。 So take a minute and talk with your peers。

 I've reopened it， and。Wch of these information can we glean from a difference of two teams。

 one has eight points and one has four points。 What do we know or do we know nothing？你都。有。跟唔知。啊主要的是。

叫我全。睇你嘅。I want to pass this around in a second， thanks。四四十啦。Yeah。All right。

 take another 30 seconds or so。Then we'll come back and talk about this。So either way， not because。

They have different skills there。个意外的。嘅我。佢嘅他 story啊。Thank you。All right， so。10。

 20 more seconds to get in some votes。And we'll talk about this。A few more。

Let's see if we can get up to the same number。There are always fewer people that vote the second time around。

 which doesn't make any sense because you can just vote for anything。

We're just looking for participation here。All right，Cool， we got some。

 we got some changing distribution。 Does anyone want to argue why they picked their answer。

it could be any of these。But let's see， yeah。I said D， because。planeins don't have like。

A fixed amount of time associated with them。 The team can decide whatever time to associate 3。

4 hours， or like 8 hours。Yeah， so， so time is time is a good metric。 So D is the correct answer here。

 There is another important metric here， which C is a reasonable answer。

 Blue has completed more stories in gold。 This is an like， this is a good inclination。

 We definitely don't want to make an assumption about the people in these teams， right。

 Story points are not an indictment。😊，You know， in just one status point about what the team has done。

 whether it's fast， slow， et cetera。 You know， you really need a history of velocity to notice any trends。

 so we can't say anything about productivity about developers。

So this's kind of leaves C and D completed more stories。

 So remember that stories in the number of stories are up to the team to decide how many points per story。

 if you complete8 story points， you could have completed 8，1 point stories。

 you could have completed four two point stories， you could have completed any other combinations of adding2。

8 So you know，4，2 and2，4 and one times4， similarly with four points， you could have completed four。

1 point stories to two point stories， whatever it may be as a team。 And so you。

 including the option that if you complete four story points iteration， you might have started three。

2 point stories and only delivered on two of those so。You know。

 we don't know by just having two numbers in the aggregate what， you know。

 what those teams were were doing。 But importantly， as a team over time。

 your velocity will tell you something。 So， you know， this is also there's。So we'll do another。

 I'll do another lunch next week after the midterm where I'm just gonna hang out and we can talk about software engineering stuff。

 But this is another thing that's interesting as a team。

 There's a lot of theory that says every time you even change a team member。

 So someone leaves your team to take another job， They switch to a late team in the company。

 you hire and grow the team So you get a new engineer， every time you change your team composition。

 you also change the rate at which your team functions and deliver stories because you have a new group of developers working together。

 so。😊，It becomes really hard to， you know understand over time exactly how to compare points you certainly can't compare points across teams。

 It's hard with a team。 but what you're looking for is over time we have the same six people。

 This is how we work together。 And that's really the point of velocity。

 if you ever take a job and you are interviewing and you somehow here that you know company is comparing team1's velocity to team twos velocity。

 that should be a red flag， because that's something that you are not supposed to use velocity for。

 It may still be a great company， but that's something that if I were in an interview and I heard I would sort of press on。

 know why are we using this metric for more than it's meant to be。

 because those are indications of sort of you know the environment not necessarily being as friendlier as conducive as it can be so。

To continue our example of login。With Facebook or something else。

 a customer once log in with Facebook integrated on your site。 Nobody is familiar with this。

 So what should you do。This is a story that if you continue working as software engineers。

 you will get familiar with， but today you are new software engineers。

 you are totally unfamiliar with this idea of logging into a third party site， what should you do？

Mod of the fact that earlier in lecture I told you a little bit about what you might go do and what you might search for。

 but assume you know nothing， what's the best thing to do here。Alright， let's take a。Seconds， cool。

 so we're up to about 45。 can we get to 50。Alright。

 so we'll call it there and we won't go through this one。 we'll talk about it。

 but I won't have you rev just so we can get through a few more things。So in this case。

 a spike is the right answer。 If you have a moral opposition to Facebook and you don't want the customer to pay you。

 C may be an option。 I have worked with people where C， in the case of Facebook has been the answer。

 That's a different story。 We can talk about it later。But。In this case。

 if you don't know anything about Facebook integration。

 it's very hard for you to break down the story。 So if you know， I know what Facebook is。

 I know what logins are。 I have no idea to get from A to B。

 If you have no idea how to get from A to B than you don't even know necessarily what to break up into the components。

 So in this case， if you if you have a little bit of an inclination。

 which you know this says nobody on your team is familiar， that is。

 know the point no one knows anything here， that's fine。

 you will all come to a point during the semester， hopefully or you are asked to do something that you don't have any idea how to do。

 that is growth。 that is hard and uncomfortable， but it is growth as a software engineer。

 the answer there is to say， I'm gonna take a day。 and I'm just gonna do a spike and do some research。

 And the important thing here is that you're recognizing that a， you don't know things。

 So it is always better to admit to a customer to say。I don't know how to do this。

 but I will go try and figure it out because that A gives you personal confidence in your abilities that you know what you can develop and then you're recognizing what you don't know。

 And then to a customer， it is honesty in the fact that you're telling them we don't know how this works。

 We're gonna go figure it out and come back to later with an updated estimate。

 so you don't overpro things。 you build trust with them is way better to say。

 I don't know how this works。 I will come back and figure it out。 And it is say， oh， yeah。

 this is gonna be easy。 And then like six months later。 Well。

 you don't have six months for this course。 But in the real world， you know， six months later。

 you still don't have a working feature。 that destroys your trust with a customer or a client。 so。

In this case， a spike is the best answer here。 So come on computer。

 So before I get into pivotal tracker， any questions on stories and story pointing velocity。

 things like that。Cool， so pivotal tracker is the tool that we're gonna to be using for this course。

 Here is a simple screenshot of what it looks like。

 You are welcome in the meantime to create sort of a demo account for yourself。

 but we will be adding you to tracker projects for each of the projects that you'll be working on and creating new ones for you。

 The reason for this is that in order to have unlimited collaborators and projects that last long time。

 you need to pay for tracker。 And so we have a special academic plan。

 which if we add you means no one has to pay for the purposes of this course。

 So you'll get an email from that in the next week or so。😊，But the idea here is that。

Trackcker is a tool which helps you plan the entire work cycle of delivering stories。

 so it helps you take stories from the client， put them in a system。

 It helps you then manage the process of going through。

 And it has a fairly specific way that it wants you to work through these stories。

 So we're gonna talk about that in the real world， tracker is a very popular tool。

 It is in some ways similar to Jra with a lot less contention than Jra has because it's much simpler and a little bit more restrictive。

 So if you've had an internship that uses Jra， there'll be some similarities and some differences。

 if you get a job after this course， you'll probably be using a similar tool。

 So each of these things is an individual story。 And in the leftmost column is the current work。

In the right most column， which there are no stories。 we'll talk about this is called the ice box。

 So things in tracker progress from right to left。 What the idea being that like when you open tracker。

 the top left view is sort of where you should focus your attention。

 and then things down below and off to the right are going to be important information。

 but not necessarily where you should direct your focus right away。And so as you go through。

 you know， all these stories are going to be organized by things that。Are iterations。

 So you'll have a view for， you know tracking which iterations you've done as a class。

 If you're taking on a legacy project， youre， you will have pivotal tracker projects that are already full of information that have some organization that the clients will hopefully already kind of be briefed on and get you up to speed。

 but you may need to reorganize things if their priorities have changed。 and then importantly。

You know， in the columns。 So we'll talk about the right most column， the ice box in a second， but。

The column on the left for the current work at the top and the column in the middle for the backlog。

 those stories are prioritized。 So you know the topmost things in the current iteration。

 those are the things that you should be working on first。

 The things in the middle column at the top of the backlog if you say， okay。

 I'm done with my stories。 I need something to work on next。

 that first story in the middle column is where you go。 So if you keep tracker organized。

 there's no guesswork about what to do next。 you always say I go from right to left。

 I grab things in the top of the middle and I take it over and I say I'm gonna start it。

 and it's going to be part of my current iteration。

 but it is a tool that helps keep not just your team organized。

 but your project organized across iteration， so。This is what a story looks like。

 We can just zoom in here a bit， but it has， you all the basic stuff that you might want to track over time。

 So it has a title。 It has points， of course， it has a requester。

 So the requesters whoever is creating the story for you guys。

 that doesn't matter too much for certain project workflows know that may be a particular person。

 it may be a product owner something like that。 It has story owners。

 So story owners are the developers of that story。 So you should be tagging your teammates in tracker with who is working on that。

That is useful。Not just because as a team of six people it will help you keep your teammates in check and make sure that you are all doing you know an equal amount of work we know that are computer science students at Berkeley and group projects so you know tracking ownership of stories helps you make sure that no one is slacking off or if someone does start slacking off you can easily say。

 hey， you know you said you get this story done we agreed to this at our meeting。

 you know what's been going on that kind of stuff。And then it has a whole bunch of other things。

 So the description is going to be sort of the main body of the story。 And for this project。

 you're not gonna to need to necessarily use labels or some of the activity stuff。

 But you have the ability to。 So labels might help you organize things by frontend by backend by feature tags at gradecope。

 We don't use tracker。 we use another tool called clubhouse， It works a similar way。

 we have a label for every single user who requests a story。

 So if any of you guys write in and say like， hey， I want the feature and gradescope。

 we will create a story or find one that exists， label the user name as the person who requested it。

😊，So that when we complete it， we can follow up with you。

There's a lot of different ways that you can use these features。

 And then the comments are sort of as a team， you might document things there like， hey。

 I ran into this while completing the story。 You know， here's something we should be aware of。

 really common thing， especially if you start by spiking a story is to write the results of a spike in the field。

 you know， any of those things are are there to use。 So there's a bit of structure。

 but also a lot of freedom in how you use it。So。Trackcker。

 when you get into tracker will have links to videos。 So if you like videos。

 there'll be some short tutorials。 There's also a bunch of articles that walk you through the steps。

 I encourage everyone to at least go through and skim those articles and videos because they are definitely some key concepts of。

 you know， a tool that is guiding you in some specific use。 tracker is not terribly hard to use。

 if you are comfortable sort of poking around with software， you will get a feel for how it works。

 But like all software， it does， you know， have its Ui quirks， it has a way of working。

 And so if it's not flowing for you， I encourage you to check those out。 And I mentioned before。😊。

You know， the product owner will be a role on your team for each iteration。

 so they will be the one who is sort of responsible for that iteration for owning the organization。

 the management of tracker， but you should all expect to share in that work。 And again。

 just to keep everyone paying attention， you know， even though this stuff is not code。

 there will be questions about it on the exam。 so。Stories。You know。

 large projects have hundreds or thousands of stories。 and we are now at， I believe。

6ix years of tracking gradecope future stories。 So even before I got there and the most recent story I is like 21000。

 So we track a lot of stuff that is not all nicely organized。

 although we try to do our best about it。 But you know you should expect that over time。

 you know this information gets logged。 So the rightmost column and tracker is the ice box。

 These are stories that are not yet prioritized， and they are not started。

 they are often not even story pointeded。 These are places where if you or your customer have an idea for a feature that you just want to make sure it gets logged。

 You put it in the ice box。 So I want to record this thing as a part of my project。

 but I don't know yet what I'm going to do with it。 it goes in the ice box。

The backlog is the middle column。 These are stories that are prioritized。 They have points。

 They have an expectation of what it means to deliver that story。 So when the time is ready。

 they are ready to be started， but they are not yet started。

 And the important thing here is that the backlog itself is prioritize。

 So this will be the product owner' job to prioritize the backlog in conversation with the customer。

 So on every software project ever。 There is always more work to do than time。 Soft projects。

 You know， willll transition between teams， product owners， customers， you know。

 the backlog is the place where it says these are always going to be the next steps And so。😊。

You know， by the end of iteration 1， you know， you'll start working on iteration 2。

 the place to start working on iteration 2 will be to look at the backlog。

 talk with your customer and say， hass anything changed， right， Pri can change。

 That's always possible。 But you know， the backlog will be a starting place for what to do next。

The right or excuse me， the leftmost column sort of where you would focus your attention first is the in progress work。

 So current stories。 The goal for this course is to have one story per person or pair of developers active at a time。

 So you should only be working on one story at a time。 Sometimes you will start a story。

 realize you need to break it down into multiple stories。 And what you can do is you could say okay。

 I understand that there's two stories active。 I sort of started this thing。

 but I have some dependency。 That should be rare。 if you're being really dogmatic about it。

 You will say I started a new story。 I actually need to work on something else first。

 I'm going to move the story that I started on to not started because it is not actively being worked on。

 and then you note that you always have one thing at a time for you or you and your partner that you're working on And so。

Again， we're encouraging pair programming， so that means you should have anywhere between three and six stories active at a time。

 You should certainly have no more than six stories at a time。

 You should probably have at least three stories active at a time。

 if you two of you are not doing work， then that is also a red flag。So the way that this works。

 so sort of again red to green， we have created to estimated。

 so estimating means story pointss are there， we have prioritized to assign。

 so one of the things that you may choose to do in the backlog is assign those to to the person or the pair that will be taking them on next started to finished so finished here means all the code is done but it may not be merged in yet。

Delivered means it's been merged in is in a state where the customer can see it。 So in your case。

 this may be merging into master and deploying it to a staging environment on Heroku。

 It could be deploying it to production。 then accepted。

 The only person who can accept stories is the customer， so。That might mean you， as a product owner。

 are clicking the accept button in tracker。 But what that means is that you have shown the customer that we have completed the story。

 We have completed login with Facebook， you know， you。Say， hey， customer。

 can you try logging with Facebook。 Does it work to your satisfaction。 And when they say yes。

 you mark the story as's accepted。 If they say no， the story goes back into development and you have work to do。

 but accepted is determined by the customer。 So in this case。

 these will be the customers for your project， you know， if you're in you know。

 a sort of nonconsultancy role。 They might be another team at your company。

 they might be the design team who requested the feature， something like that。 But。In general， the。

 the customer or the client is the person who accept stories。

 So we go from created all the way to accepted。 So what does this look like for your code。

So estimation is where you have your team meeting to assign story pointss to these story started means you have begun writing code。

 we are going to when we talk about Git in this course recommend you follow a procedure called branch per feature so that means you might check out a branch name。

 you know my project slash Facebook login and you'll have three or four branches active at a time。

Finished means that you have as a team written the tests。

 your tests are passing and any code review that you've done as a team is good。 And that's all there。

 Deliver again means deployed。 So if you're using heroroku that's merging it in deploying it to Heroku and then accept it is from the customer and then at the end of this。

 you will go through and estimate velocity。 The nice thing is because software is great at doing things for you。

 pivotal tracker estimates your velocity for you and it does so continuously so you don't have to do any work to you know。

😊，To to keep that estimation up to date， but you do have to go through and over time， you know。

 check out those charts in tracker to make sure that they tell you you know what you expect to have happened。

So we've kind of gone through this， but who's doing each step？Everyone shares in creating stories。

 you may bias this towards a product owner。But everyone is involved in those steps。

 The product owner is definitely the person who prioritizes things。 So。

 you know you dedicate responsibility to that person。 this is， of course。

 in a discussion with the customer， the product owner again represents their voice。

 but they are in discussion with the customer in terms of what should happen there。

They're also the person who assigns them you know two people on the team。 But again， for six of you。

 you product owner you're not a dictator， right， you're working with your peers。

 We are not you know despite the name product owner， no one should be starting fights over this。

 know if someone says， hey， I have some experience with the story。

 know it's a good idea to defer to them and assign them the story。 you guys should discuss as a team。

 What stuff you like working on， what stuff you might want to gain more experience with and that's a great way to assign stories。

But， you know， the product owner sort of is the person responsible for that started is， you know。

 the person who is going to be the individual owner for that story or pair will say， hey。

 I've started working on it。 finished is you know， all these are gonna be that that owner pair working on it。

 accepted is the product owner again in connection with the customer and， of course。

 pivotal tracker as a tool will always give you a velocity estimate。 And because it's software。

 It's really good at making charts and updating those live， so。We're going to ask you to use tracker。

 of course， like any tool。You know， tools don't enforce good behavior on their own。 They are tools。

 You can abuse them。 You can use them improperly。 You know， you don't， you know， if you write。

Stories that have incomplete information into tracker。

 It's not going to help you figure out what to do always。 So again， we talked about on Tuesday。

 the idea of layers， front end versus back end。Trackcker is not going to prevent you from organizing stories in a frontend versus backend manner。

re not it's not going to prevent you from assigning things in a random order to people。 know。

 you can assign stories in any way you want。 So just be mindful that if this is a tool it is helpful。

 but it's not guaranteeing success。The other thing is tracking bugs。

 So you should be tracking all your bugs in tracker as well。 Gitthub issues are a common thing。

 So some teams might use both。 But what we would really try and recommend is that， you know。

 everything goes into tracker。You know velocity as part of your project。

 you know you should be tracking the bugs and the stories delivered。

 although we'll talk about why bugs are zero point stories in a second。And， you know。

 that will just help you kind of work through things。 And then the other thing is。

 tracker is not a detailed to do list。 It is a very high level view of the work that you need to do in a project。

 So it's not going keep you on task in terms of the things that you need to do working with a customer。

 It's not going always tell you the individual details of your story。 you know。

 you'll want as a team or as an individual， your own to do list somewhere that works for you。

 It will， when you open tracker， give you a very high level of。

 you know what should be happening right now in this iteration。

 what should hopefully be happening in the next iteration。

 But it's not going to be your detailed to do list， so。That's sort of gonna be up to you。

 So the last section for today will be cucumber and cappy bar。2 very interesting tools。

 Que on stories， tracker， things like that。 What you should be doing as a team。😊，Cool。

Cucumber cucumber is a way of writing tests from user stories， so I mentioned this on Tuesday。

The idea is going to be that they are very high level。

 They read like a description of what should happen。

 and they are a great way of making sure that the story is acceptable by the customer in a form that is automattable and runable。

 They will not necessarily cover everything， but they will give you a very good place so。😊。

It is sort of the way of thinking of this。 It is the halfway point。 So， you know。

 a customer is a human who looks at everything。 They're going to look at the design。

 They're going to look at the interaction between pages。 They will have， you know。

 a sense for the feel of how an application works， right， Does this。Interaction feel correct。

 Does the navigation feel like what I want it to。 Cucumber will be the place that says， you know。

 does this thing sort of do what I expect it to do。

 It's not going to tell you whether it looks pretty。

 whether it does what the customer actually wants it to do， But what it will say is， you know。

 I have a login button。 I click login。 I'm taken to my profile page， whatever it may be。

 It'll give you good test coverage for that kind of stuff。So。What does a cucumber story look like？

 And with the caveat that this is not the best story， but it is a good example。

 We'll talk about why in a second。 a story has a feature name and a scenario。 So feature。

Useuser can easily add a movie。 A scenario is called adding a movie。

 You might want to give that a better name， but that's okay。 And you say。

 given I am on the home page， when I do this， then this should happen， When I do this。

 then this should happen。 And so this goes through a series of steps。

 And what cucumber is going to do。😊，Is it's going to translate this into a series of functions and we'll talk about Cappibar in a second but it will actually run this code in a browser environment。

 so it's going to execute the entire stack of your application。 It will make calls to the database。

 It will make sure the HTMLm is rendered properly， It will then look at the rendered HTML and say do I see that movie title there or whatever you need it to do you can do and so。

We have a story， there's one generally one feature per story。

 which can be combined of multiple scenarios。And each scenario we're going to recommend should have three to8 steps。

 This scenario is not perfect。 It's a little bit too implementation focused。

 And we'll talk about that in a second， but。Each of these steps you know will describe sort of what can happen and your work will be implementing the work for these steps so you're going to write some code that takes this text and turns it into actions that should happen on your application。

 so we're going to go through that。So we have a feature， so each story maps to one feature file。

 so these live in a directory nicely named features。

 So you know you might have a file called login dot feature， and that includes all your scenarios。

For the login feature， you might have a thing called add movies do feature， you know， and so on。

 And so a， a feature is a shared set of scenarios and a scenario is a set of steps that accomplish one part of a feature。

 And so for logins。😊，You might have a a scenario for successful logins and you might have a scenario for failed logins。

 You know， if you expect some behavior to happen when a user， let's say。

  types in their password incorrectly， that should also be its own scenario。

 So what we're going to be testing here is not just the happy path， but also the sad path。

You'll be testing sort of， you know， all the variations that make sense。 again。

 typically three to8 steps。 these should be short and readable。 They should read mostly like English。

 And what we'll work on is how we build the definitions of these steps。

 And so those live in a folder called step definitions。 You'll notice with rails。

 We give something a name。 We call them features。 There's probably a directory called features。

 We have controllers and models。 Those live in directories called controllers and models。 you know。

If there's a name， your directories in your code base should probably have the same name。

 keeps everything nice and consistent。U。There are five keywords that cucumber uses。

 and they will all correspond to the same exact function。 But。

 but you should use them in ways that as a reader of your feature file will help you understand。

What should be going on So the word given is the setup and the state。

 so given some condition in my application already exists。😡，You know。

 I'm going to do some setup work。 So given I have a movie named the Italian job。

That means that that step will ensure that the Italian job exists in the database when so when the user does something。

You know， this is clicking a button， then says then I should see this。

 so this is a step where you're going to assert some action has resulted。

 then I should see the title of my movie， then I should see a rating。

 you know then I should see my username， all those sorts of things are acceptable。

And the keywords and in but will be used to extend some of the previous steps。 So they。

You can use these sort of in various ways， but they help you say。

 sort of conjoining multiple ideas into one flow。You will use them the primary three will be given when and then。

 but you'll see all of those。The goal here is that all these keywords are aliases for the same exact method in cucumber。

 but by giving different English names， they clearly communicate what you as the author of this feature want things to happen。

Because this is code， because， you， Ruby is great and lets you do just about anything。

There's not going to be enforcement that you follow these rules， but what we will say。

 and we're going to ask you this in a second is we'll say what should happen in these step definitions means as an author trying to follow the best practices。

 what should happen there。You know， what's missing here。

 an individual scenario alone is not sufficient enough to necessarily test everything exhaustively。

 You'll need multiple scenarios per feature。 So you'll want to test adding a movie。

 You'll want to test， you know， what should happen when adding a movie fails because。

 let's say your movies are unique based on the title。 So， you know。

 we have a movie called the Italian job。 We can't add a second movie called the Italian job。

 Maybe we can， in the case of movies duplicate movies based on title is probably reasonable since you know。

 the movie industry likes to just rerelease the same movie 10 or 20 years later， because hey。

 that's an easy way to make money without being creative。You know。

 in a movie database that might make sense， you might have a common constraint of， let's say。

 email addresses on users。 So， you know， what should happen if a user tries to do something that fails is a really common story。

And it's going to be important that you check those scenarios。 So here's an example。

I mentioned login， so a secret question for login recovery so your feature will include some description This is again written like a story。

 this code is just there to describe to a human what should happen more often and so it will be comprised of a series of scenarios so we have one scenario。

That says I'm asking to recover my password。 Things are going correctly。

 and then I'm going to have a couple scenarios that say things aren't going correctly。

 How can I be sure that the user is seeing their expected errors and。

One of the things that if you've taken an HI class。

 you may have experience with is designing the state when things go wrong is as important as designing the application when for when things go right。

 if your user types in， you know， an incorrect password and your application just blows up。 Well。

 okay， that's told the user that something has gone wrong。

 but that doesn't help them figure out what exactly has gone wrong。

 So making sure that you're accounting for the ways in which you can expect things to go wrong。

 will be an important piece。 and so。Depending on your customer。

 they will be more or less strict about designing those pieces with you。

 but they will be an important thing that you should expect to work on in your application。

 So that is a bit about scenarios and we'll get into cucumber with the last section here。

 Any questions on what scenarios and features should include or should be before we move on。Cool。

We have steps。Each of these steps in a cucumber feature file will then call a tool from Cappibarra。

 which is going to run your code， run your steps inside a browser environment so it's going to pretend to be the user and the thing about this is it's going to do it a lot faster than you would by manually going through the application。

But what it's also going to do is it's going to。Look， not just at a unit test， right。

 We're not just checking。 Are we tracking login counts correctly， What we're checking is， you know。

 does the button that I'm trying to click actually exist on the web page。And if there's jascript。

 So some of you will have applications that use react that use jascript。

 that jascript is going to be run， too。 So this is a great way of。Ensuring that from top to bottom。

 your entire application works as expected。 So we talked about levels of testing。

 These are integration or system tests， and so。You know， that's that's what they'll be doing。

 So how do we write a step definition， we'll use regular expressions。

The jokes about regular expressions aside， Yes， they can be complicated。

 but they are a fantastic tool。 So we'll be providing resources over time。

 There's a great website called Ruular， which helps you practice Ruby's regular expressions。

 They work pretty much the same way that other regular expression formats work。 But every language。

 of course， has its own quirks， but。😊，So what happens here， So we have when this is a method in Ruby。

 right， parentheses are optional， so if we wanted to be more clear。

 we could wrap this regular expression in app parentheses。But what it's saying is when。I。

 so this is denoting something that is optional and not going to be captured。

 So we're not going to go through every single detail of a regx。 but this question， Col says。

 I'm not going to capture this group right here when I fill in， so it's going to match that。

Quotes are going to be these pieces and quotes。 This is looking for a title。

 This is going to be looking sorry， this is going to be looking for the string title。

 and this is going be the value that we're going to put in the title field。

 So each of these parentheses capture a group of text in your regular expression。

 and so you'll get some practice here， the applications， you know that we've released so far。

The Roten Pota application has examples of cucumber specs with some earlier expressions。On the exam。

 you'll have a cheat sheet that gives you that will provide in addition to your own that gives you awesome some of this information。

 but the way that this works is we're taking this first group， this second group。

 if we have three or four， whatever。These become arguments to our do blocklock and so each of those fields or inputs is an argument。

 and so we can say this title corresponds to a form field on our web page this with quotes corresponds to the value of that field and so Cappibarra provides us a bunch of methods which interact with a web page so fill in is a really common one that you'll be using that says find by field with the HTML name of title so when you open up a web page right every single form field will have a name associated with it。

Find the thing that is named title。Yeah， you have it has the browser has a value。

 and so you will be able to say take the value men in black and put that in the field name title。

 And so all this is going to do is simulate a user typing in men in black to the movie title field。

On your page。 But because this is a computer， remember that computers are stupid machines。

 They do only exactly what you tell them to do。 So， you know， this field needs to be named title。

 It cannot be named。 you know， title with the space or something like that。 So， you know。

 as you're going through this， there will be some gotchas that if things don't match up exactly。

 you'll need to get practice with。But you know this will be a super helpful tool and the great thing is。

When you're reading your feature file， this reads like English。

 your step definitions will be in a separate place。

 you won't necessarily need to know exactly how they're implemented。

 But for those of you taking on legacy projects， your step definitions will be a great source of documentation of sort of how the application actually works。

 So what's in these definitions， This is a call a Cappi borrowough。

 Another common thing is calls to active records。 So adding a movie to a database might be a common call。

 if it's a then example assertions that some text appears on a webp page will be a common thing as well。

😊，But basically the interactions that would happen with your application are what will go in these steps。

So given my birthday is set to， so you're setting up a precondition for the next set of steps。

 this will perhaps call update on some attributes of your of a user model and you set up that state for the next set of steps。

 so this is a call to active record， but again， you could do this in multiple different ways。

So each of these steps， we have our keyword， so remember that in this case。

 they're all aliases for the same methods， so the way that they work will be the same thing。

The first argument is a regular expression， so this is what will match the text to your feature specification。

And then it will have a block as an argument， so that will be called with the groups of your regular expression。

 so again， we have a group here that just accepts any amount of text。

 and we're going to call that the date， so if there's one group in your regular expression。

 one argument to your block in your step definition。

And then any instance variables that you set up are going to persist throughout that scenario。

 So they are scoped to the scenario again。This is cucumber and Cappy borrow doing a bunch of nice stuff for you。

 They are each you know， going to be shared， but only for that scenario。

 So every single scenario will have a set of new instance variables and so。

We'll leave it at there for today。 don't necessarily worry about the specifics of the incense variables。

 The goal here is that like rails， it should be pretty intuitive。

 each scenario is going to be run independently of another。

And so this will make a lot more sense as you get practice writing your own steps。

 and with that we'll see you Tuesday， we will have lecture Tuesday。

 but it'll it'll be new topics that will not be covered on the midterm。

 but we will also have clicker questions so you should be in lecture and then we'll have the midterm Tuesday evening。



![](img/efdf1bf07734ddf3689d6364b4d2b742_9.png)

![](img/efdf1bf07734ddf3689d6364b4d2b742_10.png)