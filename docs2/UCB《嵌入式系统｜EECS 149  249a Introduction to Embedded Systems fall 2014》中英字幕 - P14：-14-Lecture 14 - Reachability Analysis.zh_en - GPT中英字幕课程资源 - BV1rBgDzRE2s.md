# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P14：-14-Lecture 14 - Reachability Analysis.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

Okay I guess it's time to start so today before we get into class I wanted to give some summary about lab logistics。

 first of all I would like to encourage you to go on the website both on B courses and on Piazza and take a look at what happens on seven lab right and how is it going to all be organized and the line。

so。Hello。テ tick tick。Okay， so no more labs this week， Okay。

 so there are not going to be any additional lab work。So you can use the space， though。

 for the labs to start working on the project because you have all the equipment and stuff like that that you can leverage for discussing your project。

The GSI will be in the lab during the lab hours so that you can think of it as an extended office hour for the lab itself。

 so answering questions and meeting with each project group。

And there is going to be about 10 minutes per week briefing for each group so that we can keep an eye on how well you're doing and what you are coming up with。

啊。The lab right up7 which is section 6。1。3 of your manual， the hand in is next Tuesday， October 21t。

 that some of you have the Monday lab，And so it's just days we thought was too close for comfort。

 So we allow you three more days for the people who have them on life， okay， yes。I think it could。

 right。I don't see any of them。Ship by three days。 So you have three additional days。So I mean。

 if you want to bring it here， so since they are going to be here anyhow， you can do that。

 but it's not。Okay， so okay， so project guidelines。

 So it's time for you to really start thinking on the project。Because time is running and labs。

 I mean end projects are difficult to do as we all know。

 so remember that the team is three to four people their team。

So just start looking around and see who you would like to work with。

You can team with anyone in the class of your choice。

 I mean you have to be I was say at years with your group。

 you can post ideas and find groups in Plaza so you can advertise I have this wonderful idea who wants to work with me on this project that's a lot。

诶。Can be anything embedded， so can be research oriented or application oriented， as you like。

 as long as it satisfies the general guidelines that were given before。

 So pay attention to realistic timelines or don't read。Find yourself at last minute， trying to。

Weep up something that's never a good idea。Do use models to design。

 so we just don't take as a good project one， which is being done by screwdiving and hacking。

 So we would really like to see a thought process and a modeling part and a simulation part of your of your design。

And we would like also to again， to encourage you to have a good quality software architecture。

 which means。Decompose your program well， plan a testing strategy and comment your code well okay so this could be also considered as an exercise in good programming practice as long as we are looking at embedded systems so remember that the embedded system requires a different way of thinking because of the importance given to a physical properties that are associated with the software。

 so the way in which you come up with a good software architecture for embedded system is not necessarily the same good architecture for general programming。

So you have to think along different lines。O。And choose your hardware very wisely so just pick up the among the list of parts that we gave you。

 pick up the ones that are really going to be good for your project and good for you that you can work with so a timeline and deliverable so October 21 you have to have a project chapter which means groups and a outline of what your project is going to be。

November 4th is going to be a project review with the GSI and mentors。

 if indeed you find a mentor in the department or wherever else。

 you will have to qualify with us if this is okay or not。

 but if it is an okay vote on the mentor and the project， then you can meet with the mentors。

November 17， project mini updates。IWe would like to see where you are F and what is going on in your project。

 November 25 is a project milestones。 so you should have already。

Good progress on the project itself and December 17 is project presentation Now we will start here for because is we have three hours of use of the class for exams is not going to be enough because you are one half million right people here so three hours is not going to be enough so we also reserve other rooms to continue on so the idea is to have you present for about 15 to 20 minutes your project。

And we would like to see everybody involved so that you can see what your fellow students has done and you can comment on it or have a feeling of how the class is going and so that is going to be on December 17th right so there was a question on Piazza say are we requested to be present at all presentation of course you are not requested。

 but we would like to see you so for at least three hours of the class I mean of the exam。

 we would like to see all of you here？Then after that， you may have other exams。

 you may have to study something， whatever， so I understand if some of you misses it。

 but we would really like to see the maximum amount of people being presented as representation。

I remind you that in addition to the great where it's going to be for the best project。

 I stick to my promise， it's going to be a nice bottle of Italian wine for the winner。

But more importantly， for some of the best project， since there are many。

 So it's likely that something good is going to come up。And so that's something good， you know。

 in general。 I mean， I'm used to this since 40 years ago。 but for the best project。

 we aim at publishing a paper in conferences or in journals。According to what you come up with。

So think along these lines。 So maybe for some of you， the first。

Chance of having something published Okay， so think along these lines as well。

 so find a good project that can expose some of the material that you learn here。

 but can have that spark of originality that can be the subject of the publication in good conferences and journal okay。

So December 19th is a final report plus video plus peer evaluation。

So that's the very last moment in which everything comes together。 Okay。

 so let's move on on on the topic of the class。 and today we are going to talk about reachability analysis。

 yes。Yeah。No， no， we said that we give you guidelines， right。

 So the guidelines were the list of hardware and stuff that we。That we allow you。 So don't。

 don't go away out of this set of hardware learn that we gave you。

 So instead of thinking about exact project， we say， okay， take this。Platform has been。

The starting point for your problem。Originally， we thought to give only three projects。

 and everybody had to pick one of these projects。But that was at the very beginning。

 that then we moved towards the idea of using platforms that are the same for everybody。

 right So the list of parts is the same for our everybody。So also because by doing this。

 we allow you to be creative on the application and at the same time we keep it limited in the sense that you don't go everywhere and anywhere you want。

 but and plus you get also the design methodology in went with。Presented。

 which is this a component So build up something good out of the components and show me that you have verified your approach。

 But you are right。 At the beginning， I was more directly， okay。Allright。

 so reachability analysis so。Last time we were talking about temporal logic and how temporal logic is a good way of imposing properties to your design。

 Now that's fine， you can formulate properties with temporal logic and we say that formulation is already a big problem but once you formulate what do you do with it so remember that one of the good thing that we wanted to say is that if you have formulated your properties in a good way and in a formal way。

 then you should be able to verify。That your design satisfy this property。

 but theyve been captured in a formal way。 So today is about that。 So how you could do that。 Okay。

 and some very important results that were obtained in the last 20 years about how you go about verifying this property。

So I remind you that a typical problem that you may have in robotics on in other application of embedded system is the fact that you want to reach a particular end state and you don't want to end up being stuck in any place so you want to stay away from a bed set of states and want to be capable of reaching a particular state that is your goal state。

 additional problem we said before is that instead of reaching only a final state you may want to have an intermediate set of states that you want to go through。

Now， all of this。Forulations can be done in formal terms， as we said before， in using temporal logic。



![](img/cc7db1e6cedfa922a813e7504fdd7b9e_1.png)

Now this one is another interesting application what you see here is a graph of finite state machine modeling of two trains and a bridge traffic controller so this is actually a German railroad and the point is actually was actually done so this was a formally verified design of the scheduling of the trains and of the bridge controller and so the goal here was to to avoid。

E collision path。 guess what。 Yeah that would be nice。

And we know that sometimes the trains do go on collision patterns。 So a few years ago。

 there was a miserable accident happening in New York State and when two train collided because of the wrong scheduling of。

Exchanges and green， semapho and red sephos and the like。

 So it is possible if you don't plan it carefully。Okay。

 so this one was a result by this guy or its hammer University of Munich。

 so people do use this technique to avoid accidents and re。



![](img/cc7db1e6cedfa922a813e7504fdd7b9e_3.png)

Now reachability analysis， what does it mean Reability analysis， Well。

 semantically is obvious is that I would like to see where I can go。

 you know how far can I go on my finite state machine。

 so I start with a state and say well which states can I touch？So this is a set of reachable states。

 whatever state that I can bump into now。If I could do this analysis。

 then of course I will be able to solve the problem that I showed you before。

 because if I have all ver reachable state， if any of ver reachable state is a bad state。

 that's bad news right so it means that my system as an hazardd。

 I may end up in a bad state so the tutorine may collide， not good by the same token。

 if ver reachable state contains the end state says okay， I can reach my goal So allelujaia。

 So by doing reachability analysis， I can solve both the problem stay away from the bad state any insurance that I get where I want to get。

Okay。So。Model checking is actually an algorithm that is capable of verifying formal properties。

Along the site of reachable states。 Now， mind you， model checking is probably one of the most used technique in verification that I know of。

Shartest simulation。And the interesting point is that model checking has earned the people who propose this technique。

uring the touring Award and touring Award is like the Nobel Prize of computer science。

 So this is indeed an important thing。 Now， remember with temporal logic。Was， again。

 earned a touring award for Amy Nuelli， and this technique。

 Mo checking earned the same award for three people was Emerson， Clark and Sifas。Okay。

 so these three people were credited with the idea of developing this technique。 Okay。

 so what is a formal verification then？Well， the first thing is that you have to start from the model of your system now。

Remember that we would like to see whether and there all possible condition in which my system work that some good or good stuff happens or bad stuff does not happen。

The point is that when you think about all the possible conditions。

 what does it mean all the possible conditions？Does it mean for all the possible inputs that we can dream of？

Not really， what we have is that whatever the environment to the system can provide as input to the system and their analysis。

Which means that I have to have a model of what the environment does。Okay。

And when I do a formal verification， I'm going to combine two models。

 the model of environment and the model of a system。So that I form what is called a closed system。

 so it's all inside one blob right so the environment and the system and I want to show that this combined system has got seven properties so the system and environment come in you compose this two models now if you have finite state machine for both allelujaia we know how to compose finite state machines so and we would see some example of how you do thats we already。

Had classes on how you compose finite state machines so that is reasonably well known。

 then you get a closed system what we call M and then you have the property ases temporal logic and then you have an engine which is called verify。

 but it going to see whether P applies to M if P applies to Mis you'll say I have a working system if it doesn't work then the good thing about model checking is that it will give you a counter example。

So I will tell you where it fails。Why is that important or interesting because it's a debuing mechanism right So if I know where it failed。

 I say oh， I see what happened and so to prevent that from happening， I need to do ABCD right。And so。

 in fact， this can be used to do synthesis。So that you never get into a bad state。 right。

 and that will be the last light of a class。 How you do that， and you do my control。 Allright。

 so closed system again， is that you take the environment and the system combined。To together。

 And then there is no input anymore to talk about， right。

 because the input is contained in the world model。 So。

Model the entire world in which you are interested in。So again。

 you would you obtain a cross system by composing the system and the model of the environment。

 And now you are all set to go to do reachability analysis and the。

So suppose that you want to model check GP， which means that probabilityp has to be globally true on all states。

 right？Now， on all states means on all the states， that is。On a trace of a system。

 which means for all reachable states。So let's say consider an Lt L formula from GP where P a pre。

And P， remember， is a property on a single state。 So G means that that property on a single state has to be valid for all the states that a rich。

To verify GP on a system and I need to enumerate all the reachable state and then for every reachable state I have to say yes no。

 it holds only doesn't hold if for any reach if for one reachable state it property doesn't hold then GP is false okay if it was for all the states that I can reach allelujaia its okay。

Now， notice yes。没。Now， that is a temporal logic， It's not a property， So the original property is。

 I mean。When we talk about P and we say GP， that is。Call it a global property。 But P。

 when we say we use in temporal logic。The proposition is on a single state。Pos。Exactly， no， no， no。

 no。 It's a propositional logic。 So it doesn't have the time involved。It doesn't have time involved。

 In fact， G is a proposition。Is atomic proposition right on the single state， right。Okay。

 and G P is a probability。 That is。Okay。Trajectory， so it involves time， right。

 so you have to express N G is a temporal nature， right。Only okay。

 to verify G B datada and check with P through the state space Expr is typically represented with a graph。

So what happens is that I start from this state0， then I have 22 states around me， so if I go here。

 that is one step and so the graph is in beginning of my trajectory。

The next state of miterject I take another step， and by doing that， I build a graph， right。

And so that graph is called the reachability graph or state graph of the system。Now。

 when am is a finite aid machine with searchability analysis terminate。Always there。In theory。

 what would do we say in theory， it does terminate an Azo in finite time。

 The problem is that you may have what is called the state explosion。

So you may have so many reachable state right and so many things that you need to look at。😊。

That in practice is almost if you had an infinite set of things to do。

 So you will never be able to do it。 So this one is also called the curse of dimensionality。

And it is one of the major impediment of using this technique for any problem。

So remember when I say brute force never works， so if you apply brute force。

 which means you are going to look at all the possible states that you reach and you are going to visit all of them without thinking about it and your state is representing the tiny little details of your implementation。

 you are out of luck， you will never be able to verify that system so you have to stratify use layer of abstraction and every layer of abstraction。

 you have to have a reasonably simple problem to look at。Because then the techniques will apply。

 and you will not be out of luck。 And so if you have a certain。

Relations between the properties a different layer of abstraction。

 then while you are moving down towards implementation， you still keep the state space small enough。

 you are guaranteed that in the end when you compose back everything the original properties are satisfied okay so that is very important point to say meaning then when you get to form a verification and the like you always have to have a guiding principle which is。

Design methodology， So freedom from choice。 limit your。Choices， because otherwise。

 it's going to be too difficult to do anything。 In fact。

 the number of states may be prohibitively large， And so you may not be able to perform the complete analysis。

Now let's get back to our nice example of the traffic light controller and the property that you would like to say is globally true that green and crossing is not true。

 why green and crossing is bad news because it's green for vicars and the pedestrian walk right？

Not a good idea。嗯嗯。Bad news for a pedestrian。 maybe for the car driver。 Yes， finally， get to turkey。

 Well， you know， if you go to eat， you， you've got to watch out because that。😊。

That is not that property is not necessarily verified，But we are in United States and in general。

 if you're a Turkey pedestrian that crosses the road in the middle of nowhere with a freeway North car stop so this is an amazing feature of Berkeley in particular right。

And anyways， so in fact， I got flged by police， there was a guy which was about this far from the border of the crossing。

Right，And he was walking towards it。 And I was coming and just crossed。 I just went。 So police are。

 you didn't give president to begin。 say， wait a me。

 The guy got to the crossing when I was to the next cross。So， I didn't。

Try to kill him you know I mean why should I stop if I stop I stop everybody else right and so sometimes you have to optimize right a little bit because otherwise you stand till and it takes 35 minutes to do free miles like myself this morning right to get to work why because sanitary project right that's not good It's not optimized It's not good embedded project zero to a city of Berkeley they are failing Okay F grade so don't do it in your project So I'm going to check personally。

 It's something like reset said all right。So coming back to the real story。

 even though that is a real story。 and this one is an abstraction of a real story， so。Okay。

 here you have on the left the model of the traffic light and on the right you got the model of the pedestrian okay so now which one is an environment and which one is a system and their design is rather clear。

 the pedestrian， I would like to design a pedestrian， the ideal pedestrian never crosses。Stays put。

 so cars go right。Anyway， so but we have a model， which is the model of the pedestrian。

 which is the environment， and we have what we are designed。

 And so the composition of the model of the pedestrian and the and of the traffic like controller should。

Give you that。Notion of the fact that you never get into a bad state。

 which is a bad state is where not green and crossing occurs right Okay now。

We compose the finite state machines and you get this finite state machine here。

 notice that this simple turkey problem is got by itself 189 themm states so 189 when you think about you you compose a machine with 1。

2，3，4，5 states on one side and three states on the other one， when you multiply in all of that boom。

 189， why because if you do not an extended machine but a finite state machine。

 then for every account you have a new state。Msday， Tuesday。 So you got to。To consider that。

 So in any case， this a compact representation of the combination of the two finite state machine。

 you have a variable which is count0 to 60。And then you have the following state space in which you can start anywhere you want。

 so initial state， so suppose that you start from red crossing。And so until the count reaches 60。

 you stay there。 So you have the cell loop。And the pedestrian can cross and then when the count reaches 60。

 you set to zero counter so you reset the counter and you go to green and none。

 meaning no pedestrian is going to cross。Now then you got to count again in green and then you go to pending and waiting。

 meaning that some pedestrian shows up， then the counter goes up and then you go to the next state which is yellow waiting now if pedestrian doesn't show up you can go directly to green to yellow because you want to have some regularity which traffic light goes from green to yellow to red so this very composition of a two machine。

Now， reachability analysis， we would like to see again if I can get into a situation where I can see the pedestrian crossing and the light is green。

 So now you always say， well gee， we have a finite aid machine every I show I just go tom tom to tom to tom and I see what happens So unfortunately 189 states to do tom tom tom tom。

 you don't have enough space on the whiteboard， blackboard computer screen to main okay。

So what happens is you have to think as a computer thing。 So a computer doesn't have eyes。

 So the actual。Representation， graphical representation of the state doesn't mean make damn difference。

 So it doesn't care。Now if you think carefully what is the best way of representing a finite state machine。

 we want to give all the state one by one and the arc that go from one to the other not really what we would like to do is to give the rules according to which you generate the next state and so remember that we have two functions right so actually a relation one is the next state relation for nondeterministic finite state machine or。

A function in the case of dataministic finite state machine。 given where you are。

 I can tell you where you can go。 right， It's a next state function。

And there is the output function that says given the state in which you are。

 given the input which you are， that's what you're going to see at there。

So we serve the implicit rules。Where give you the famous graph。 that is implicit。

 I give you through functions。Now， then when I do reachability analysis。

 what I'm doing is essentially applying these rules， right。

 applying next state and I get the next state。which could be single state for a particular input。

 a set of states nondeterminly， or if I want to see for all possible inputs I'm going to see only the next state function in which I'm going to quote unquote。

 consider all possible inputs that can present to this state right。That's the way in which I。

Construct the state graph on the fly。 So I start from initial state and then tune to kun， kun， kum。

 I generate the various states。So we start with initial state and explore of the next state using a suitable graph strategy。

 So suppose the time state。0， okay， so at the beginning。So， now。I have a bunch of next states。Right。

Next to me。Remember that I want to explore the reachability， right， So how can I。Explore this。

フネしているまし。For sure， I have to take a step。Boom， right。Now， I can do two things。

 so I can go back to stage 0 and generate the next。And I conduct state 0， generate to the next。

 So what I'm doing is that I'm exploring all these states which are distance one。

Which is called breath first search。So you do like this。 Youre like a fan， right。

 You're opening a fan。 So everywhere I can go from this state。

 I generate what is other and you don't ask， What is the other， the other strategy so。

That is called depth first。 So your friend here said， go to the end。 So what happens he said。

 I'm here， I go here， then I don't go back and say， where can I go from here to the next。

 and I pick one。And then I say， where can I go from here on and I pick one。

 When can I go from here on and I pick one， So let's call depth first。Now。

 when I see something that I've already seen， then what do I do。I back up to a pre state。

 and I do another step。So that's a way in which I traverse。That first is an incremental strategy。

 which tends to go all the way to the end。As many times as as I can， right。

 The other one is that I go everything， everything， everything， everything。 Now， which one is best。

Either one， right， it depends on the particular graph that you got， right， And so， in fact。

 there are deep graphs in which that first。And shallowgraph， where breakfast is much better。

 Okay so you cannot say a。So either one will work。But in the case of implicit techniques。

 most of the times it's better to go breakfast for the following reason。 we see how it goes。

So with that first search， we say before you maintain two data structure。

One is the set of visit state are， So iss a set of the states that I've seen。

And then I stuck with a current path from the initial state。 So I went through state 1。

 state 5 state 7， state 22， right， and I'm in state 22。Now， if I generate state x。

 which is the next state， I may be state 5。 guess what。 I already visited it right。就。I don't。

ステイステイクンィフトの。That is the way in which the stack is working now。Why do you want to keep the stack。

Because you want to know where you have to back up， to start another search。

And then when the entire stack has been listed， you have this。

OkayNow that's the reason why you need this stack。 not only。 supposeupp that I。

 when I do this step first， I get into very bad state。

Remember that I wanted to have a counter example。What is the counter exam？The content of a stack。

 that is a path that violates with property。 So here we go。So that's the reason why you。

 you need this duall。How to say data structure that you are going to use， the set of state earningss。

So if the depth first algorithm finds the target state， okay。

 how can you generate a trace for initial state to that state， You read the stack。 and that's it。

 We already say it。 very， very simple。Simply read rhetoric。Now嗯。

This is also called a explicit state model checking example。

 So why explicit because we have an entire graph in front of us。

 so we are not generating it on the fly， okay。So because we want to show what happens。 So you start。

 first of all， you have to pick up an initial state。 So in this particular case。

 the initial state is red crossing  zero， count 0。You are red。

Traffic light and pedestrians are crossing。 It's initial state。

 Now the next one is red crossing and you bump by one the counter right and then the way in which this finite state machine works is that you keep on going until you reach 60 right。

And that is which are all the selflo。 So let's first。And that is， no matter if it is breakfast。

 that first。There is only one path。 so doesn't make any damn difference。Now， once you get there。

 if you want to do that first， when you say for example， I get I go to green nu， okay， green nu0。

 green 9，1 and so on， right green nu 60。 And then what do you do Haha now you have two paths right。

 two potentials。 you can go yellow waitinging or pending waitinging right。

So if I do that first I choose one of the two in this particular case。

 say we do if I remember correctly the slide， we go to yellow weighting， Yes， I go， yellow weighting。

 yellow weighting five， and then you move on。But if you move on。

 you get to red crossing and you already seen that state， so what you have to do。

 you have to back to the previous point， which is green N， and you generate the next state of green1。

That you have not visited before and the next state that you have not visited before is spending waiting and so you stay there one up to 60 now once you are through waiting 60 what happens you go to yellow waitinging right but yellow waiting you are already seen so this is it。

That's the complete reachability analysis。 That's the all。

Traces that you find the graph of the state。 right， space。 And that's it。

 So you have concluded the analysis of the。Now the symbolic approach is different one。

 and so this one actually came later and there was the key guy into this was Ken McMilln that has been a lecturer in this department and he was at the Cadence Berkeley La。

Any other idea。 And he said， okay， now。Can I use a particularly efficient。Data structure。

To represent Boolean functions， to make this search faster。And， in fact， once he had。

Applied this methodology in this thesis at one of the ACM best theses of award。Now， he said， well。

 if I can do that， then the number of states that I can deal with is going to be。Very large。

And the answer is yes， if the finite aid machine is brand is large， some sense， it's broad， right。

This is certainly true。 And in fact， it showed it was a paper kind of tonguey cheek that he say that he could explore in very quickly。

10 to the 30 states， right，10 to the 30s in uongous number， right。

It is more than the molecules that are present on the earth。 It's uongousness。And but E demo。

 you can do it easy。But， you can do it。 So anyway。But the point is that instead of doing this explicit search。

 I'm going to represent all the next day。喂。In a compact way。

 or this is the idea or it's just representing things in a compact way。So now in order to do that。

 you had to convert the problem of visiting states in a logic problem or in a Boolean function。

 because you remember that this particularly efficient Boolean structure applies to Boolean functions。

 So I need to convert virtual analysis into a Boolean function representation。Okay。

 so set operation can be performed using Boole and algebra。

 We know that represent a final state S by its characteristic function， which is a Boolean function。

 What is a characteristic function is a logic function that evaluates to one。

If x belong to the state S。 So a set of state S。 So we have a set of state， which is called S。

And we want to see whether state X belong to this。四。That is the characteristic function of x。

So F of s x is equal to one if and olive leaf。But if and。

 if in the sense of definition is not a themy。 So it's a definition。So if x belongs to S。

 this function is equal to1。Now， it a Boole function， all right， Okay。

 so I can represent this brilliant function with this fantastic representation。But now。

 the interesting point is that this characteristic function， we if we want to say。

 does x belong to the state S。 So the answer for reachability analysis would be does which state belongs to a reachable set。

喂。And so how do I then convert that into this question。Well。

 remember that the next state function or relation is exactly what gives me what I can reach in one step。

 right。So what I will do is that I will keep on doing like this and ask the question over and over again。

 does x belongs to。That set of new reachable reached set。

 So what I need to do is that I need to increment at every step， the set of rich state。

 And I keep one asking， does x belong to y。So， but if you think carefully。

I can represent the next state function as a Boolean function， in what sense， how does that work？

Because。If I'm this state， I'm going to encode this state， right？With the不。Representation。

 so suppose that we have， let's make four states。How many bits do you need to represent four states too as your friend here。

Rich men with no nose bullolean function， really well， too， right， because I have 0，0，0，1，1，0，1，1。

 okay。😊，Now， if I want to say that I go from stage 0，0 can reach 0，1 and 10， how can I express that。

Is I just price as a relation right between the bits。Of the states。

The next state function is going to be the Boolean function， as as。Domain0，0 and S range 0，1，10。

And I can build that with cubes with whatever， right？

So I wont tell you how this efficient data structure works it's called BDD binary decision diagram。

 you can represent any Boolean function with the binary decision diagram now you know I bet all of you know about the Kne Mclaskey minimization procedure and the way in which build a functional logic function with cubes right？

And cubes are essentially， know， vertex， vertices。This particular case of the square。

 that of any boolean hyper。So you can cover any logic function with points in this。Cube space。

 and then you have a sum of product representation on the logic function。 but there is another way。

 which is called BDD。 And if you want to know more about BDD， I'll just tell you what it is。

 you can go and take 144 and 144 will tell you about what a BDD is。At this point。

 for this class we suffice to say that there exist programs。

 we do that based on this very efficient representation of bullant。Okay。

And the Boolean function of interest are the next state function。 That's the only thing I can。

 You know， that's what I'm going to represent。So the symbolic approach of Brad first search is you generate a state graph by repeated application of a transition tank。

 So I get at once all my next state。 And then of all this next state。

 I'm going to get all the next date and so on。 So it's called Brad first because all of a sudden you find。

 you know this。😊，Veryry wide that it keeps on growing。

 If the core state is rich stop report success as continue until all states are seen。

 So you go from Q0 to Q1 by repeated application of deelta when you go to Q2。

 then Qk and if you get S Aleluia， and then there is a way in which can trace back。

The set of states that you need to visit to get to us。For example。

 if you want to generate the content example。There is a way。 I'm not telling you how to do it。

 but there is a way。Okay so the symbolic reachability algorithm then is very simple so you start from a set as0 and so a reachable set of s0 is as 0 right it the beginning then I build an algorithm。

 I do a symbolic search so I call r new equal to R so the initialization of the algorithm while r new is different than the empty set what I do I say r new is the set which is which consists of the state that I get from one step。

But。Purified by the things that I've already seen。And so of course this is set new state so I eliminate the states that already seen and whatever is left is the set are new why then I focus on our new because when our new is empty means that I visited all the states so that's what it says so r is our union are new and so you loop around while our new different from zero I repeat that operation over and over again and then I add。

So this one is a symbolic， it's called symbolic again。

 because the representation of the next state function and of the set is based on this implicit representation。

Which is called a Bo decision day， binary decision day。Okay。

 so binary decision Gr diagrams and Booleion satisfiability is another technique to figure out if the state belongs to。

Set of states。 So is another way of doing reachability analysis。

And that is yet another way in which you can do that bulletoleant satisfiability actually works very well with that first search binary decision diagram is the implementation of Brad first search。

Now， there are programs around， many programs around that you can download from many universities in Netherlands web platformss。

The implicit search of the finite state space。There are pros we do in the open domain。

 we do this analysis。 Now， interesting enough。There are also proprietary programs that work on trying to verify properties。

 temporal logic properties on finite state machines。

 and the name of a game is to be able to cope with problems with our。

Essentially difficult because of a number of states。 Now。

 remember what I told you that sometimes the depth first works better。

 sometimes that first works better。By saying tokens， sometimes satisfiability works very well。

 sometimes。The BDD technique works very well。So what do these programs do。

 The one that cost one gaziion dollar if they to buy， they use combined techniques， right。

We try one and when we see who doesn't look too good when we switch to the other one。

So it's a continuous pinimpponing between different techniques。

 and so it's a heuristic So the way in which you deal with the search is heuristic。

 the most important thing is that in the end you got to reach all reachable states because otherwise you don't solve the problem so sometimes people use heuristic to say。

 well， it works it doesn't work now in this case， the heuristic is in the way you go about。

Doing the complete analysis。 So it's a different thing。

 So you are not cutting corners on the final result。

 you are trying to invent new ways based on intuition or whatever that will give you the right answer in the fastest possible way。

 So its not a dangerous。Euristic。The dangerous heuristic will be，um looks good。 This is O， right。

 That's very dangerous， heuristic， very dangerous。You can get yes。Its still still out。

So what I said is that there is now both of the V two problems in general RP complete， right。

 so no lack exponential in the worst case， in the worst case。

So not all problems exhibit the worst case。 And so that's the reason why you ping pong between the two。

 There may be particular problems where both of them don't work tough luck because otherwise we would prove。

P equal to NP p， which is impossible to prove。 right， so that's impossible to prove。

 Nobody is even being able to start the proof along this lines。

 So it it's very unlikely that p equal NP P。 I don't think it will be ever possible to do that。

 but there is no proof to the contrary so。One of these interesting logic problems but the question is that this is a hard problem no matter what satisfiability is the father of all or mother according to what you like best is of all the three of NP complete problems it's the root of the three so is the mother of all bed situation let's say。

Now， yet， if you look at some programs that turn around， for example。

 I don't know how many of you are design logic circuits， but if you use synopses design compiler。

Or which originated from here from Berkeley with a province called Miss。Now。

If you look at any of the sub routineoutines that are in there， they always solve NP complete。

One way or not。 yet it goes， right， we can solve 100000 gate optimization problems。

 We can solve a million gate now。Million gate problem。 Now。

 if you think in terms of Boolean functions， the size of this Boolean space is immense still。

 we can do it。Why， because we got the right heuristic to visit the space。

And so that was a secret sauce in。Mega lesson to you guys。 So for your future。So if1 says O G。

 this problem is impossible to solve because it's NP complete。You say maybe， maybe not。

This is not an impediment to try to solve the problem。😡，Okay。

So you can find ways in which by using very good techniques。

 you can get to solve the problem in most of the cases。

 which in most of the cases is what you're looking for anyhow。So donkeyは。

Now not even when the problem is undecidable， which is you know yet another horrible thing with respect to NP complete。

 don't be scared， go at it because if you do indeed find the solution。

 allelujaja now then after two days go by or like we go by or a month go by and you can say a definite answer then you declare defeat and then you try to say well looks good okay。

Now this the last result is all this looks good， okay。Don't try right， but you know， when it comes。

 it comes。All right so and this is very important because if you， in some sense。

 it's very good to use formal techniques， it's always extremely good to use formal techniques and to use para properties。

 but sometimes are a good excuse not to work hard enough。😊，Don't do it。

 So in application you always have to find the way to go around the difficulty。 One way。

 as we say before， is to space so an N complete probe。Okay， I was thinking it was rain。 Now。

 it's not just falling leaves now。The point is that if you have a limited space。

 even if it is exponential， if I have。Say 10 variables，2 to a 10 is not that big of an number。

I can do it， right？So even in the worst case， I'm still okay。So the point is that。

 how can you be clever to reduce this。Size so that you can go about it。 That's a youistic。

 One possible way of solving the problem reduces taste。 Okay， we' see how you do it。

ok嗯 boom boom boom咁啊 o。So set of reachable state， this one is symbolic model checking。

 which you say variable red and variable2 is crossing and count is the other variable。

 so if you say the next state from the red crossing is described by this logic function。

So which is the ending of different enclos。 So that is the logic function gives me the next day。

So count less one， count less than 60。 And so， so that is。The logic function。

 that generates the next day。Now then I or， so I get all the states that I can reach when V1 is green and V2 is equal to none and count is equal to 0 to count from 0 to 1 and then I can do V1 pending and V2 weighting n count equal to1 and then I keep on repeating when I can replace v as v1 pending n v weighting n0 and count between 0 and 60 so I'm building the set of reachable state in an implicit way and then once I reach count to 60 when I go to the other one which is v1 yellow V2 weighting count and count equal to0 count less than 5 is all the states that I can reach from V1 yellow and V2 weighting and that is the entire set of reachable state describe with a boolean function and which you would do it and that representation of boolean function can be。

D熱。So I told you， we want to restrict the space。 So I mean， this is trivia， right， so we can do that。

 believeieve me，189 states is nothing， but。As a principle， what trick can we do to reduce the space。

The trick that we can use to to， to reduce the space is to say。

What really matters for the problem at hand？So if I'm going to discuss， I don't know about pedestest。

 and I don't care about cars， Can we remove the variable cs。From the description of the system。系。

If it doesn't matter what the condition under which I go， the counter， it doesn't matter。けないリミネートあれま。

Now， if I can do that， then all of a sudden dimension with drops down almost nothing。

Now this one is called localization right and actually Bob Ken。

 who invented this simplification technique， did this while it was in Berkeley。

 in fact it was implemented in this and we have gazillion papers talking about these localization techniques。

So simpler models have smaller state spaces are easier to check。

 The challenge is to know what can be thrown out。And so a simple user approach is called localization abstraction。

 which means get rid of all the variables that are not present in the formula that you want to。

That you want to prove。So you hide the state variables that are irrelevant to the productivityivity you want to prove。

 Now， is that。Sure technique， does it always work。Unfortunately， no。Okay。

 so if you localize in this way， you may still have some of the hidden variables。

But make it different。Especially because if you high variables。

 when all of a sudden you get non deterministic machines。

And so if you take one path instead of another one， you can say everything is is bad， you know。

 because you have always， you know， non deterministic choices。

But may be still okay because that path you are not going to take that remember since I eliminated the variables that are going to differentiate between him and him。

I don't know。 So every time I hit a counter example。

 I should re the model and see if that is a real counter example。 or no， if it says fine， aeluya。

 I'm sure。Because what I did is that I created a larger reachable set by doing the simpl。Absolly。

No no， in fact， and we do No we do， but I can say I can answer the fact that my system doesn't have property fee why。

 because the nondeterminism that I generated is a fake nondeterminism。

 It's really the original machine was deterministic。

 It became nondeterministic because I threw away variable。

 so I may say that my property is not true because I reach him。

Because I don't see the path that takes me to him。 and that path may be an invalid path。

Because I abstracted， so he became reachable。Exactly， and so now you have to back up。

 But when you do a localization abstraction， you don't know if you abstract。Is there uistic。

 I to say this is the way in which I'm going to abstract。

And that is what I'm saying is that it sounds very reasonable。 You say， Aeluja， that's good idea。

 What I'm saying is that， yes， it is。But no he may not be。 So if the answer is going to be yes。

 we're probably satisfied when you're sure it is okay， which is very good。

 If you get something bad because I get to him he' the bad guy， then maybe that the indeed。

 but maybe that the sequence that gets me to him is an invalid sequence。

 So Im never going to hit it right。But， I need to。Explore it。 So every time I have a counter example。

 I traceser path and I explode， I come back to the original graph along this path。So it's like I。

 you know， I take a very high level view。 and then all of a sudden and then I need to go with a shallowello lens。

What happens in the， O。So that's it So this one you see I threw away almost everything right this finite state machine has got through through through through all over the place so because there was no variable that was of winter to me on the input and output set so what this says is simply saying what is reachable but doesn't say how and so if indeed I see the bad state red and crossing right。

It doesn't mean that the red crosssing is really ir reachable。Because this is everything goes。

Allright， so a safety properties say nothing bad ever happens and a finite length counter example。

 now a liveness property remember that we have two set of properties that we may want to assert on the system one is safety that means nothing bad happens so I don't hit the bad guy instead the liveness properties is that I keep on getting the good guy。

So now which one between the two you think is simple I already told you that， you know。

 it's written down that liveness is a bastard of the bastard of the bastar of the bastarter of the problem。

 Now， safety is easier。 It's still a bastard problem。

 but it' is not a bastard of a bater of the ba of the bastard problem， okay so。

We have three level of buster less in the safety clock。 and in fact， if you look at papers。

90% of the papers talk about safety properties。And you wonder why， because liveness is again。

A very complex one。So now， suppose that we have a robot that must pick up multiple things in any order。

 So you want to pick up item I where I is one from N。 How would you state this in in。And。

Tempor logic。Any wild idea。So I want to make sure that I pick an object up，Yeah， he's right。

 So what I want to say is that F eventually。I get to P1， So I pick up one object。

And then he says and。So F of P2， because I want to go through P2 as well。But remember in any order。

 right， So that's the reason why thank God is。Com。So that's it。Okay， that1， blah， blah， blah。

 You can actually also kind of nest this proposition。

So how would you state this goal in temporal logic， we can also do this。

 The goal to be achieved is actually F of p1 and F of P1 and da da。 So you can nest it。

 is is the same thing， but is more complex。 So suppose we just want to say eventually I get to P1。

 So eventually a pickup object1。So how would you go about doing that， right。

 So because this eventually is kind of an。Funding properties。 Remember what is very good to。

 do to state everything in global， right， Global is good right because it's safety。Global is good。

F is not so good， right So is there a way in which I can take this F31 and convert it into a global。

We already decide when we did temporal logic， does anyone remember？Yes。Right， exactly。 is not G。

 not P1。Exactly， so here it is。31 is not g， not31。 And so therefore I can construct the counterexemper to G。

 not31， and the counterex is a trace。 I guess we're over to a good place。好，再见。Very good。

 So I see that someone is reading the book is following the class。Or already knewer that。

 which is not fair。

![](img/cc7db1e6cedfa922a813e7504fdd7b9e_5.png)

Okay， so this， this is the the last discussion。 So by way， if you want to， for example。

 suppose that you want to。Consstruct a control there。They gets you to free one。How would you Okay。

 So we know that G of not p1 is a counter example right？ So it gets me where。

 So what do what would I do to build a controller So something that makes my system go what I want。



![](img/cc7db1e6cedfa922a813e7504fdd7b9e_7.png)

So that is a control strategy， isn't it， so they say which will get me then， so with race。

So what you do is that you create the input， the controller will create the input that will generate that time。

 right。So all of this， there is always two。Faces to the coin。

 The two phases of the coin is that one phase is verification， and the others。Face is sink。

If you're looking at formal techniques。They really are very much related to each other， right。

And so in fact， if you look at all the literature， it talks about controller synthesis or formal verification of temporal properties。

Essentially， they use the same technique。Essential， right？Because if as we saw here。

 there are two phases of the same coin。 and the same coin is reach。Set and how you。

Reuce or inlar reach abilities。Said， if you have。A bad state。

 which can be reachable or if you have a good state， which cannot be reached。

And so all of these give information how you should set up the controller。So the synthesis problem。

To do what you desire to do。 And remember， where control is a is a wonderful thing， right， because。

You have a horrible system right， that may explode in your face。

 You know what is the most horrible system from stability point of view that man has ever created。

And still works。Is a fighter jet plane， he is so unstable， you would not believe。

So with no controllers， the thing will crash in one nanoce。

And why is so unstable because unstable means？啊。Really fast。 maybe too fast。 right。

 And so what happens is that you want the thing。To change state， right。As quickly as possible。

 So if you have an unstable system。 or boy， you just boom move that， right， So then you say。

 stop before you crash， please， right， So control。So if the controller takes an aible system。

 that's whatever it wants to do。And it's going to make it do what you want。Now。

 then you look at all the literature of control， and then you see what a controller really does。

And he's amazing in mind boggling what the controller really does。

Is to erase the original system and to replace what you want to do as the real system。

 It's simply erasing。 I just canceling completely original system。

And then if you look at all the mathematical techniques are how you are going to kill the original system。

So the famous controller for finite aid machine is essentially same。

I don't care what the real system does because I'm going to eliminate it anyhow。

So and you are replacing it right so it's like you know this thing where you take bacteria。

 when you get it out， you put the new DNA and you make it do things， so it's the same thing。RightYou。

 you are getting the your system out and youre replacing what you like to do。

And it's amazing that it works。It does work， otherwise plane would not fly and car would not drive and all this nice stuff。

 but if you go to the bottom line， I mean this will never be said in any class on control theory。

 but is what it is。So that reread your control manuals and stuff and try to interpret in this way。

 then everything will come crystal clear。All the techniques in you know are related the notion of control we observed all came down to this very simple principle。

Okay， so let's it for today， questions。Apple， oranges。 so I don't get to eat today。All right。Yes。

 there was a question。No， you indeed like。Was an involuntary motion。



![](img/cc7db1e6cedfa922a813e7504fdd7b9e_9.png)