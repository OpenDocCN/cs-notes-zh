# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p24 -24-Guest  Lecture - Factor Graph Representation for Hybrid Perception Problems -BV1UfAmeUE3e_p24-

![](img/06f1a46e5c06b9a5d9f37a2d76644563_0.png)

Yeah。Hello everyone， it's my pleasure to introduce you Dr。 Kevin Doherty of MIT。

Today is going to give a guest lecture on faculty graph representations for hybrid perception problems。

Kevin has done a lot of nice work in the slam and mapping and。Even marine robotics。

And that's where you started I remember your early works right so I remember Kevin from the time I was working on Gasian processes mapping and he did a really cool work you put it on a3 data structure and it was suddenly 3D and nice。

嗯。And then from there it's been just。Re new， interesting works every year。

Looking forward to your talk and I'll let you take it from here。Awesome。

 thanks so much for the introduction money hello everyone。

 this is super cool to me just to be chatting with all of you today。😊。

I'm getting a little bit of echo， I don't know if there's someone oh， okay， there we go。

So for this talk， I'm going to give a little bit of a broad overview of just my research work to date just to like familiarize everyone with you know what my interests are。

 what I work on that kind of thing， and then I'll do a deeper dive into some more technical stuff dealing with some of my recent work on factor what I'm calling factor graph representations for hybrid perception problems I'll go into all of you know what that means more specifically in the context of the talk。

But just to contextualize so my background， I did my bachelor's in electrical engineering at Stevens Institute of Technology where I graduated in 2017。

And then immediately went to I came to MIT where I was pursuing my PhD jointly in the MIT Aastra department and then also as part of the Applied Ocean Science and engineeringing department within the joint program between MIT and the Wood Solarographic Ins at MIT。

 I was part of the Marine Robotics group， which is within CAL of a computer science and artificial intelligenceence Lab working with professorssor John Leonard there。

And yeah， also I should note I just I just defended my PhD thesis this past December and I've wrapped up at MIT now。

 so I'm officially no longer with MIT， but broadly my research interests kind of lie in the space of robot perception。

 estimation， navigation， machine learning and then also with application in areas like field robotics and marine robotics。

 and then even going down into especially more recently mathematical foundations like dealing with specific optimization problems or spectral graph theory as it appears in slamM。

 which has been tied into some of my most recent work。So so what I do now。

 actually as of literally two days ago， I work on this robot， which is the Boston Dynamics Atlas。

 so two days ago I started at Boston Dymics where I'll be part of the Atlas research team working on you know relatively similar problems to the ones that I thought about during my PhD。

 which is in a very different context， dealing with things like objectbased robot perception and navigation。

 but more guided toward doing complex two-hand manipulation tasks。

So I'm very excited to be getting started there。And of course if anyone has any questions about any of this。

 you can feel free to reach out to me， Im happy to share mommy has my email information or things like that if you want to share you know with the class folks can reach out to me about any of this stuff。

 I'm happy to talk about technical stuff I'm happy to talk about career stuff， anything at all。

 feel free to reach out。And then to give a little bit more of a grounded sort of overview of some of the research work that I've done while I was an undergrad at Stevens。

 I worked on real-time predictive mapping for field robots and this is some of the work that Lonie was talking about where were really trying to deal with really two sorts of problems first is in the marine setting when we have something like a sonar sensor where data is particularly sparse and very noisy how do we build a coherent and ultimately useful occupancy map from that know often tremendously noisy data and then the second problem which is shown on the top here is kind of on the opposite end of the spectrum which is how do you similarly how do we build maps but in this case where we have actually a tremendous amount of LDAR data and in this case the question really is how do you ensure that you can update your map quickly as you're getting large quantities of data very quickly So this is like two ends of very opposite。

Enends of the sort of data spectrum， if you will， for these sorts of robots。

And then when I came to MIT and Woods holele in 2017。

 I sort of shifted gears toward working more on semantic representations for both mapping and localization。

 and so this included things like object based slam。

 underwater terrain classification and things like anomaly detection for marine robots。

And then my most recent work， sort of the last couple of projects from my PhD that I did。

I was working on efficient inference techniques for what I would call more expressive and robust models for robot perception。

And this was building off of some of my earlier work on object based land。

And this includes generally problems like combining learning based perception methods like object detectors right with traditional geometric state estimation in the context of navigation。

 also includes things like how to mitigate outliers and then in maybe the most general case how to deal with discrete states of interest like contact。

And then on the fundamental side， or maybe what we might call like mathematical foundation side of things。

 I've done a whole bunch of recent work on convex optimization techniques and spectral graph theory as they sort of connect to the estimation problems that appear in slam and in robot perception more broadly。

 for example， to establish formal performance guarantees on the quality of the estimates that we can provide in the context of slamM and then also to sort of leverage those ideas to develop new graph courseification techniques for large scale slam so as we collect more and more measurements。

啊。We want to ensure time bounded slam performance and memory bounded slamM performance。

 we need to get rid of some data somehow and so how can we maybe inform a method that picks and chooses which measurements to keep around。

And then in terms of like long-ter research goals， maybe to give sort of just a picture of know who I am as a researcher。

 I guess， I'm particularly interested in the perceptual algorithms and representations that we need to give real robots the ability to operate robustly over extended time horizons without human intervention。

And so the reasons why I care about this in particular， and again this is not an exhaustive list。

 but three areas that I care particularly about are scientific exploration and monitoring。

 infrastructure， inspection and maintenance and things like sustainable food and agriculture。

 and I think in order to achieve some of the really important or I would say some of the most important objectives in these spaces。

 we really need to be able to go beyond the small spatial and temporal operating scales mapped environments and frequent human intervention that sort of characterize the current state of the art in real robot deployments。

And so that's a little bit about kind of my interests and like who I am and like I said。

 if you're interested in any of this stuff， you know feel free to reach out。

 but specifically in the context of this talk，I'm only going to discuss really one and a half major projects。

 which is dealing with inference and hybrid graphical models and connects some of the work that I've done on robust perception and semantic method。

And this work was done in collaboration with some of my lab mates at MIT， David Baxter。

 Eddiedie Snieweis， Zichi Luu， Kin Singh， and then of course my advisor when I was at MIT。

 John Leock。So to kind of set this up， my thesis work was really largely motivated by the following sort of problem。

So let's suppose we have a robot that's just tasked with exploring a previously unmapped environment。

 and this could be something like a coral reef like I have picture here。And so in order to navigate。

 our robot needs to know， first of all， where is it in space relative to this environment， right？

And thens where's all the stuff in the environment of course。

 and finally it might be important for a robot to have some idea about what everything in its environment is right so maybe a robot needs to be able to identify different species of coral or different objects of interest in its environment。

And it's easy to see how this sort of general problem setting could be adapted to more specific problems right naturally this captures applications and things like environmental monitoring where maybe we want to assess the health of briefs。

 things like mine countermeasures where we want to detect and localize mines infrastructure inspection like in the case of aquaculture where maybe we want to detect specific changes or degradation。

And this of course， also shows up in important terrestrial applications like autonomous driving。

 a lot of us are probably familiar with these types of applications at this point where our autonomous cars need to be able to keep track of buildings and other cars and pedestrians in order to get from A to B。

And then also in the case of something like a household robot where we might want a robot to perform object centric tasks like washing the dishes。

 right in order to wash the dishes， a robot needs to be able to like find the dishes in the first place。

And mathematically， we can formulate this problem as a particular type of simultaneous localization and mapping or slamM problem。

And this specifically is the problem of inferring a robot's trajectory and a map of the environment from a set of measurements。

And so we want to know a robot's trajectory look。Sorry， do we have a question。

I think someone may be just accidentally unmuted。嗯。So in our case。

 we want to know our robots trajectory， the locations of a set of environmental landmarks。

 and then in our case the semantic class or category of each of these landmarks。

 and so this makes the problem what we would call in the business semantics land problem。

 just this edition of classes or categories of each object。

And of course because all of the measurements that our robots can make about these sorts of quantities are noisy。

 so maybe this could include things like camera images。

 inertial measurements obtained from accelerometers or gyroscopes。

 you know whatever your robot happens to have access to。

 we specifically formulate this problem as one of Bayesian inferences and so given all these noisy measurements we want to find the most probable set of robot states and the most probable math。

Okay， so what actually makes this difficult and I think that there are two things that I'm going to focus on in this particular talk。

 but obviously you know there are many challenges broadly to doing all kinds of navigation but the two that I'm going to be interested in the context of this talk are first incorporating semantics in the context of geometric traditional what I'll call traditional geometric estimation in S and this is tricky because predictions from learning based models that we use to obtain semantic information like object detectors can be unreliable in practice and this is especially true when these models are deployed in settings that don't really match the training data that they have available to them。

And so here on the right we can see one at the time state of the art model giving erratic predictions in what I think is a very reasonable situation。

 so here this is Yolo from a few years ago， I think this was like three years ago now probably a new state of the art model would would do much better。

 but here it's this is just an off thes shelf Yolo model running on data from an iPhone。And giving。

 I think， pretty。Ptty wild predictions you know it predicts that the sofa is also a mouse it predicts that a guitar is a person and so on and so forth And I think what's interesting about this is that this isn't really an adversarial environment at all right this is just my old apartment so it seems like。

If we want to use these sorts of predictions from learn models in the context of navigation。

 we need to somehow reason about uncertainty， however it's going to appear in these models。

And this leads to the next important challenge， which is。Once something goes wrong。

 how do we deal with it right how do we deal with outliers or incorrect data association that might arise from these sorts of errors because you know if you're willing to take me at my word for the fact that you know these models can be unreliable or if you've maybe used them and experienced this in practice。

 we know that this can be the case。嗯。But even beyond that。

 these models can also be ambiguous even when they're performing well。So for example。

 on the top right here， we have two detections of cars and you know I think I would say that this model is clearly detecting cars。

 but it's not actually clear from these bounding boxes which are here depicted in green。

 which cars are being detecteded by this model。And so in this case， data association。

 which is this establishing the correspondence between measurements that our robot makes and landmarks in the environment is challenging。

And of course， we want to use these techniques for a navigation system。

If if our robot is is trying to use cues like objects in the environment to detect whether or not it's in the same place that it's been in before this can lead to catastrophic failures and this is what we see exactly appearing on the bottom right here we have just a sort of sample example of a。

A robot's trajectory depicted in green here and a map which is depicted in gray。

 and as we have outlier measurements， which are these red lines。

 what you can see is that there's significant distortion in the quality of the map that the robot is able to produce。

And of course， if we want our robots to be able to determine things like outliers or data associations。

 this requires solving a discrete estimation problem。

 and so this is kind of important because both dealing with semantics and this problem of outlier rejection or data association involve reasoning about these sort of discrete sources of uncertainty or discrete sources of ambiguity。

And so。Really the question that we sort of posed。In dealing with these kinds of challenges is how can we represent this coupling between discrete and continuous states。

 So first of all， how can we you know， model。How discrete sources of uncertainty or discrete sources of ambiguity interact with the usual sort of continuous sources of uncertainty that are common to all kinds of sensors that we might traditionally use in a navigation setting。

 like your accelerometer or camera or LiDAR， ettera。And so we'd like to， first of all。

 be able to represent this sort of coupling。U and then ultimately， as I kind of alluded to before。

 find the most probable assignment to the unknown states that we're interested in。

And as I'm kind of alluded to， a natural way to approach these problems is as maximization of the posterior probability of in this case now we've kind of observed a set of continuous variables。

 which I'll call C and a set of discrete variables D， given a set of noisy measurements。

 which I'm calling here Z。And I've already kind of posed the semantic s problem within this framework in a way where we have continuous states corresponding to our robots trajectory in our landmark locations and discrete states that correspond to the semantic classes of landmarks。

 but also outlier rejection fits into this framework where we have continuous states corresponding to our robot's trajectory and discrete states indicating inlier outlier decisions about measurements。

 as well as problems that involve discrete contact states like gate estimation。

And throughout the talk I'll also this will be useful to know。

 I'll use the color red to depict discrete states of interest and the color blue to depict continuous states of interest so whenever there's an unknown state like say a robot's pose that would be a continuous state of interest which would be in blue and then a decision variable like whether or not a measurement is an inlier or outlier would be depicted in red and you'll see that and I'll call that out as it sort of appears as well so that's clear。

Okay， so given this sort of formulation of， you know。

 we want to maximize the posterior probability of these continuous and discrete states given measurements。

 how do we actually go about modeling that posterior distribution？Well。

 it turns out that a lot of these problems actually emit very elegant and concise descriptions in terms of hybrid factor graphs。

And factor graphs， which I think maybe you've covered in class already。

 are simply probabilistic graphical models that provide us with a flexible approach for constructing complex joint distributions from simpler components。

And by hybrid， all I mean is that these are factor graphs that contain both continuous and discrete states of interest。

And as I said here， I'm depicting those discrete states of interest in red and continuous states of interest in blue and the measurements that a robot can make or constraints。

 even sort of modeled constraints between variables are depicted as these factors in black。

And so for example， this sort of first first case here on the top is an example of what we might call a switching system where we're trying to track the motion of continuous motion of a pedestrian in an image。

 say subject to some discrete decisions that they might make about whether to go left over。

 this is maybe a little bit of a contrived example。

 but on the bottom we have actually much more realistic example of something that you might see in practice。

 where we're trying to estimate the trajectory of a robot given by these continuous variables corresponding to the robot's pose at different points in time。

Liinnks may be bias some odoometry measurements that the robot has access to。

I know robot also makes these loop closures， but we might not trust that those loop closures are reliable。

 and so we introduce discrete variables that control whether or not we're going to treat those measurements as inliers and keep them and use them for state estimation or effectively discard them as outliers。

And ultimately， we'd like to perform joint inference of all of these quantities in the factor graphs simultaneously。

And so unfortunately， even though hybrid factor graphs give us this。

Fairly expressive way of writing down some of these problems。

 the sort of common off the shelf tools that are used for solving continuous optimization problems defined in terms of factor graphs like you might see GTSM or G2O or series。

I havenn't previously enabled solving these sorts of hybrid problems， at least not directly。

And so as a practitioner， you might be able to use an existing technique for a specific problem。

 so maybe you're dealing with the problem of outlier rejection for which tons of existing solutions are available and you can go on GitHub and colonary repository and you're good to go。

 but if you don't have a problem that fits nicely into the mold of some existing technique。

 you might end up trying to change your problem somehow by say transforming discrete states into continuous states just to use existing tools。

 which is obviously not desirable because now you're actually having to change something about your problem formulation just to use the tools that you have available to you。

 which seems a little bit backwards。Or in last case。

 you end up implementing your own ad hoc tools for a specific task。

 which is fine in the immediate context right because at the end of the day you can implement something that does what you need it to do。

 but ultimately this leaves the next researcher or know next practitioner to hit the same roadblock and this is kind of the situation that I found myself in a few years ago。

And so to give a little historical context and maybe to demonstrate that this motivation isn't like totally fabricated or contrived。

 this is a real exchange from the GTSM users Google group from back in 2020。

 and I don't have the context from the original poster here。

 but the original post was asking essentially about whether it's possible to use the tools in GTSM for factor graphs containing both discrete and continuous variables and here Frank Dellard。

 who some of you might be familiar with from Georgia Tech who is responsible for this GTSM library。

He's saying， yeah， you can mix any factor types you want using our software。

 but we don't have any optimizers for this and so if you can imagine me as a grad student three years ago working on these sorts of semantic s problems or object-based s problems。

 this really got me thinking like how can we implement an optimizer using these tools that would be sort of relatively general purpose because I was struggling with some of the issues that I mentioned on that previous like？

啊。And so it's interesting to think about why there isn't really good support for these types of models。

And I think that one of the key reasons， at least， is that it's particularly hard to identify a suitably general candidate for influencing modelss。

So even if we happen to be able to write down the sort of factor graph model for a switching system or for outlier rejection。

 if we wanted to perform exact inference for hybrid models in general。

 this is almost always computationally hard in the formal sense。

And the reason for that computational hardness is simply because the number of discrete assignments is going to scale exponentially with the number of discrete states。

 and in the worst case we have no choice but to essentially explore that state space。

So existing techniques are often either computationally intractable。

 but maybe they can offer guarantees， for example， by trying to explore this this entire space or they're forced to simplify somehow and so for example this could be by pruning the hypothesis space in some way and actually the method that。

That Frank is alluding to on his post to the MHIM2 method。

 which is very cool where by Michael Case's group， does essentially exactly that it attempts to prune this discrete hypothesis space。

But the key consequence of the difficulty of exact inference in this context is that existing techniques typically trade off efficiency for robustness。

 and I particularly like this quote from Chris Atkinson， a professorfes at Carnegie Mellon。

 he asked us once after a talk， it really stuck with me and influenced。

 I think a lot of the ideas that I worked on during my PhD。

And he said referring to slamM systems in particular。

 he said these systems have the property that the more they know which is the bigger the maps are the stupider and slower they get and that's troubling so how do you deal with that and this is I think an interesting question to consider in light of these sorts of hybrid estimation problems。

So to address this in our work， which we call DCSM。

 we developed a set of general purpose tools for representing hybrid models in terms of factor graphs。

 and we also propose an efficient algorithm for solving these sorts of hybrid estimation problems。

And then to cap it off in this presentation， I'll cover a novel semantic s system that we developed that leverages some of these ideas and the tools that we built in our DCM library to do some cool object based navigation。

So in particular， this DCSM library， which stands for discretereet continuous smoothing and mapping。

 is written in C++ and it extends the GTSM library to the setting of hybrid factorograms。

It also incorporates as sort of a default optimization technique。

 the optimization method that we developed that I'll talk in detail about here。

The library that we developed I think this is also important。

 is easily extensible so you can easily model new problems， you know not necessarily semantic slam。

 for example， or build new hybrid optimization methods using a unified underlying representation so even if you didn't want to use our optimizer like say you wanted to develop your own optimizer you can write a different optimization technique that ingests as as input the same factor graph that another method takes this input and this is really cool because it actually allows you to compare for example how different optimizes would perform on the exact same problem in a way that wasn't really possible before without well I should say wasn't possible but rather wasn't really convenient because if you wanted to use multiple different techniques for doing hybrid optimization in this setting before you'd ultimately end up writing a lot of sort of middleware code just to interact with different solution methods and so what's nice about this is you can sort of。

Down one factor graph model。And then optimize it 10 different ways and see what works best。Of course。

 right now we only have one optimizer， but it would be very interesting to think about trying different optimization techniques in this context。

Okay， so how do we actually solve these optimization problems because I've just I've just kind of laid out why this is so challenging。

How do we actually do it？I see sorry， we have a question in the chat。

What does stupider for a large map imply， is it like large error game or it stops using history after a certain point？

Let me think about that。I think so maybe to backtrack。嗯。Let's see。Stuper yeah okay。

 sorry I to think about that for a second so what Chris is saying here when he says the stupider and slower they get。

 what he means is that these the performance of these methods is getting worse as these maps scale。

 meaning you're more likely to see， for example， an error smaller large in your map。

For the bigger the map is and by bigger we're really using the bigger the map as a proxy for longer duration operation typically so it is essentially exactly like you said。

 you'll see larger errors， both larger accumulated errors or a higher likelihood of dramatic errors。

 as the maps become larger as duration of operation becomes longer。Maybe that answers the question。

Amy， related status。Stupidity question。Can we also say that？We expect we add more information。

 things should get better， but it doesn't most of the time it just doesn't and that's very disappointing。

Yes。That's a wonderfully concise way of putting it。Yeah。

 it's exactly that we more measurements should make。Your state estimate better。

It should make navigation easier， but in fact， in practice what we often see is the opposite that the more measurements you have。

 the more likely you are to encounter unmodled errors and those unmodled errors are likely to corrupt your state estimate significantly。

So as our robots navigate longer， collect more measurements。

 this is troublesome and we'd like it to be the opposite right we'd like to get to a point where where we can fully realize the benefits of having more measurements。

And one more question here， I mean， there's a historical reason for it。

 but I remember a time that everybody in slam estimation they had to implement their own solve。

They refuse to use any of the shell optimizer whereas in。Let's say control community。

 if you told about using an aftershell solver， you had to just formulate your problem。

Do you think it's time to port our s libraries as an option to professional salaries？

What do you mean by professional solvers a lot of people， for example， work on。

Control multi agency system and they might use grouprubi or some solvers that you know it's a mixed integer program you just program it and you're done or it's a V program you're done they like a lot of the solvers that you want for example the one you develop but be still very disconnected from those libraries I think that there's there's maybe two things to say there。

U。One is that I think that commercial solves don't。

Naturally provides support for a lot of things that are useful for folks who work on perception and estimation。

嗯。For example， at least on the research side of things。

 if you're doing things that are a little more tried and true。

 like if you're doing extended columnman filters or something like that。

 it can be there are tools that exist that have been in circulation for a long time that you can probably pull and you know use things like that。

 but if you're doing research there aren't I think as many tools or as good support from say commercial libraries for。

You know， say doing like factor graph like doing optimization for an objective function that's parameterized by a factor graph and we'd like to do dynamic updates to that factor graph we'd like to do incremental inference all of the things that sort of pop up in。

A contextt which I guess you might consider relatively niche in the grand scheme of things like。

 you know， we want real time online performance out of our stay estimators often。

And that's maybe a requirement that's not always true of other of other domains controls。

 I think is a good example of a domain where。It's it's clear that those problems are important enough that it was worth a dedicated effort to develop really good commercial tools maybe sal will get there I don't know it's hard for me to say I mean it's clear these types of problems are important right the second thing that I would say。

Is that？For the case of factor graph。For the case of a factor graph specifically。

 I think that there's there's definitely an interesting trade off between using an existing tool for。

You know， being able to write down your factor graph in a relatively general way。

And then just you know solve it versus I want something more performance and so I'm going to develop specialized tooling for to solve a particular problem that I have you know maybe if you know working in a company or something like that。

 maybe there's a very specific type of slam problem you have you don't necessarily need to the entire GTS stack or something like that to to or you know the entire power of factor graphs but maybe you can write just to fix lag smoother and you don't even need to necessarily reason explicitly in your mind about the fact that there's a factor graph under the hood but you know really there there is I don't know if that makes sense。

 but I guess what I'm saying is。There's。There's a tooling question here， which is， you know。

 should we use these sort of commercial solvers or you know， that kind of thing。

 but but there's also a question of。We can still use， I guess there's also a question of translating。

The factor graph as a modeling tool to software， which I think is actually maybe。

You don't necessarily what I'll say is I guess you don't necessarily need all of the software tooling to implement all of the different features that factor graphs can afford even though even if your problem is nicely parameterized by a factor graph so long as say you know you have a particularly maybe like a specialized like a particular problem of interest so it may be worth it like in the context of DCS maybe this this will ground my response better like it's not necessarily important that you use I'm not I'm not for example concerned if people use our library DCSM I think that the important insight and the insight of our technical approach that I'm going to go into is to write down the problem clearly in terms of a factor graph model and then you can go from there you can see if there's any sort of special structure that you can leverage when it comes to implementing the software or that know the underlying algorithms to solve that problem so at the end of the day it's like write down the model and then figure out all the software stuff the goal with the DCSM thing is really。

And similar to things like GTSM is really to provide a fairly general interface。

 which would be useful to， I guess research practitioners。

 mainly might be who might have a changing problem specification。Thank you。No problem。

 that was a great question。All right so okay so I've kind of laid out you know that this this is a hard problem right so how do we actually solve this the sort of insight that we leverage in our solver that's implemented in DCSM。

Is that while these problems are often generally computationally hard。

 it turns out that they often split into subproblem which are easily solved and specifically these sub problemsms can be formed based on the conditional independent structure that appears in the factor graph model。

So for example， an easy way to see this is， I think probably clear in the second example of outlier rejection。

And so what we like about one one particular thing that we like about factor graphs is that we know。

That if we say if we consider， say these two discrete states in red。

There is no path from one of these discrete states through the graph to the other that does not go through any continuous state。

 and so if we happen to know an assignment to these continuous states。

Inference over the remaining discrete states becomes fully decoupled。Yeah。

Now this is nice because this actually now splits into actually independent sub problems that we can solve。

 And so here if this you know we're interested in。In myer outlier decisions， say。Now this problem。

 which was quite difficult to solve， because it involved reasoning about all pairs of inlay outlet decisions。

 and you can imagine in practice， we often have far more than two。

Now we can actually just solve each of these inlier outlier decisions totally separate。

In the case of the switching system， we see a kind of different story。

 and so it's not actually obvious immediately why this might be advantageous。

 but here conditioning on the continuous states， the subgraph over the discrete states is simply a chain。

 and we happen to know that in the case of a chain。

 the general algorithm for exact inference in discrete factor graphs called max product elimination。

 simplifies to what's known as the Veteria algorithm。

 which maybe you've seen in glass or something like that。

 which it happens to be a polynomial time algorithm。

Which means that this discrete sub problemblem solved step can be performed in polynomial time。

 even though inference over the joint inference over the whole。

Factor graph is worst case exponential time。And this is also for these particular cases。

 I'll go into a little bit more of the sort of analysis of the computational complexity of doing this a little later。

But it turns out we can play this game in the other direction as well。

 if we fix an assignment to the discrete states， we can always optimize the continuous states efficiently and so in the case where our measurements in middle linear model this might involve convex optimization or in the more common case of nonlinearar measurement models。

 we would simply take a step using a trust region method and so if we consider this probability distribution over the continuous states conditioned on the measurements and an assignment to the discrete states this would involve essentially computing a gradient of this probability。

And taking a step in the direction of I gradient in the in the most in the loosest possible。嗯。Case。

And of course， we don't actually know the correct assignment for the continuous and the discrete states。

 so it may not be immediately obvious why this would be useful because if we happen to know that off the bat。

 the correct assignment for continuous and discrete states， we would just be done。

 we would have the solution to our problem。But we can leverage this idea in any case。

And so the way that we'll do this is essentially by supplying in initial guess to the K US states。

W here's the noted as CI and the way to visualize this is that the sort of x and y axes of this plot are giving us the continuous state space and the Z axis。

 which just has values maybe at like you could say zero or one for two possible assignments。

 the Z axis corresponds to an assignment to a single discrete state。

So this would be for a factor graph with two continuous states and a single discrete state。

And what I'm plotting here is just the value of the joint probability where darker blue is higher probability and going all the way to red for low probability so here if we supply an initial guess which is now and sort of just an XY coordinate given by C what we're going to do is is solve for the optimal assignment to the discrete variables conditioned on this estimate for the continuous variables and so here it may be a little hard to see from this but。

Because this upper plot has a darker blue， we conclude that the higher probability assignment to the discrete states is to set D to one here。

 so that'll be our DI plus one。And then given our update to the continuous states。

Weheat will solve for the sorry given our update to the discrete states。

 we'll solve for the con states。And so here， the way to see this is that now we live in this sort of top plot and we'd like to now compute a gradient with respect to this contour。

 take a step in that direction， and then that gives us CI+。

And it's important to note that you don't actually need to compute the precise maximizer in each of these sub problemsble。

 in fact， to guarantee that you're never going to make the cost of a solution worse。

 it suffices to say that each of these subpro doesn't make the cost of a solution worse。

So in other words， when we update the discrete states。

 we don't ever go to an assignment to the discrete states that is not as good as the current assignment。

 and likewise， if we use something like a trust region method for the continuous states and we can guarantee that we take a descent step。

 that's enough to guarantee that this overall procedure never makes the solution worse。

And a lot of you will have actually seen this idea in practice before。

 so the iterative closest point method， which maybe you've covered it in class as well。

 is probably the most popular algorithm for solving the point cloud registration problem。

And this essentially proceeds by positing an initial guess for the unknown relative transform between two point clouds。

 and then we're going to use that to determine an estimate for the corresponds between the points in each cloud and then we rinse and repeat this process。

AndThe cost function for this is depicted on the right here。

 and this should be minimization over not just a rigid body transform in SE3。

 but also the correspondence variables here DI， so this should be a joint miniization not minimization of just the post。

Now it turns out that if you encode if you simply write out the graphical structure of this objective function。

 you get a factor graph that looks like this where the discrete states are those decision variables in red。

 the correspondence decisions， and this single continuous variable is the rigid body transform from one cloud to the other。

 and then each measurement which is each term in this summation is one of these factors。

And so ICP or iterative closest point will just perform alternating optimization on this objective function。

 right， but this is also exactly the algorithm that。

DC Sam employees and so if it turns out that if we。If we program up this factor graph using DCSM。

And then hit optimize what we get are exactly the results that ICP would give because mathematically this is equivalent to running iterative closest point in this case。

 and so these are actually results from running effectively ICP by way of DC SAM on the top and this is the Stanford Dragon data set and here I'm just showing five iterations of optimization where in between each it we're doing a continuous step and a discrete step。

And you can see that you know， we get pretty reasonable results where。

 you know initially we have these two separate red and blue point clouds。

 and then they converge to something that looks pretty reasonable。

This is obviously like a you know very easy sort of case， there's nothing special about this ICP。

 this is like the most basic ICP implementation you could possibly have。

 but it I think gives it a different view on the sort of optimization technique itself。

 which is that you can kind of think about this loosely as a generalization of the idea behind ICP to arbitrary factor graph topologies。

So all you have to do as a practitioner is encode this factor graph and then you can hit solve and you're effectively getting。

 you know， the behavior that that。We would get out of something like ICP。

And the really nice thing about this approach， which I think has been observed by folks who have been doing point cloud registration for a long time。

 is that it easily scales often to many thousands of discrete variables without any need to prune discrete assignments。

And so here I'm showing that using a very simple conditional Gaussian mixture outlier model。

 we can achieve competitive performance on a robust slam task while being faster than a state of the art approach based on graduated non convexity。

And so specifically here， we're trying to estimate the trajectory of a robot。

Sor of I guess a sort of simulated robot that's navigating around on a sphere。

But a subset of the measurements are contaminated by outliers and so here we have 2500 about 2500 discrete variables that simply control in a binary fashion decisions about whether measurements should be treated as inliers and kept in the optimization or treated as outliers and they're still kept in the optimization but but。

Moodeelled with a very， very large variance， so almost effectively removed from the optimization procedure。

And you can see across the top here that in just a few iterations our method recovers a pretty reasonable solution。

 these red lines are outlier measurements and then in blue are the inliers。嗯。

And then here you can see our approach is giving very very good performance in terms of error。

 this LM approach is just a standard Lunberg Markrot。

Optimizer that that has all of the outliers in the graph。

 So this is doing no reasoning about inlier outliers。

And then here you can see the time on the time plot。

What you find is that our method in red here is about as fast as just the vanilla sort of continuous optimization technique that doesn't reason at all about outliers。

 but ours is also know keeping track of these inlier outlier decisions and part of the reason for this is that by making good decisions about measurements that are inliers and outliers during course of navigation the sort of overall cost landscape seems to be a little less chaotic than when you have tons and tons of outliers in the optimization process。

Okay， so I mentioned I would come back to this when is our solver actually efficient because I said you know I made all these claims about sort of computational complexity of different parts of this problem。

 how does that maybe generalize so specifically our solver as it is currently implemented is efficient when conditioning on continuous variables creates small or sparsely connected sets of discrete variables because really as I kind of mentioned before it's this discrete subgraph that's contributing to the computational complexity of this problem。

If the discrete subgraph is densely connected， global inference is just going to be hard so if you had say like a single factor that's connected to all of your discrete variables and you had a whole bunch of discrete variables then in that sort of factor graph topology。

 it's going to be quite hard to find I should say in that sort of factor graph topology。

 even the discrete subproblem optimization step will be hard。However。

 there's sort of a way that we can get around this。

 which is that in the current implementation we're solving for the optimal discrete assignments conditioned on a set of continuous states。

 but we don't need to do that， we can apply local optimization。

 just like how we take gradients with respect to continuous variables when we're doing local optimization。

 we can apply similar techniques like coordinate asscent or disscent to the discrete subpro。

And as I said， all we need is improvement in the sub problemsble to guarantee improvement in the joint assignment。

 or at least that we don't make solutions worse， I should say。

And then that leads to another interesting question which is when can this method guarantee good solutions and we can't generally we can't is sort of the answer in a nutshell and it's a simple fact that even in vanilla what I'll call vanilla slam meaning just continuous only s problems。

 we typically solve these problems using local optimization methods that don't have the ability to make guarantees on their performance except in some restricted cases under you know restricted noise models say。

And that kind of thing， but in the most general case。

 we don't have those sorts of guarantees and of course， because our our approach。

has vanilla s as a special case， you we can't do any better than that。

And so the takeaway really is that in order for our approach to succeed。

 we crucially need a good initial guess， just like when we're solving vanilla s problems。Of course。

 in these types of hybrid estimation problems it may be the case that it's a lot harder to supply a good initial cast right so in the future I think some interesting things to consider might be for example。

 blending the sort of local optimization procedure that we developed with globalization approaches like search or like differentneing procedures and things like that。

To try to either mitigate sensitivity to the initial guess or at least to explore the sort of landscape of possible solutions better than supplying a single initial guess。

And then I think。I'll mention just briefly for folks who might be interested why or where would I use DCSM in my own research if you're you know a practitioner who's interested in maybe trying out DCSM or something like that。

 why might you use this I think from the solver side。

DCSM is cool because it allows for efficient incremental inference， and I haven't mentioned this。

 but I'll talk a little bit more about this actually in the back half of the talk。

Partly the reason that we're able to achieve efficient incremental inference is because by separating these problems we're able to leverage all existing tooling for solving continuous estimation subprom。

 so you may have heard of things like ISM or IM2 and we can just simply use those tools for solving continuous estimation subproblem。

DDS allows you to easily implement backends for things like semantic mapping， localization slam。

 robust slam， all that good stuff， I think it'd be interesting to do things like combine learned category level factors like shapepe priors with geometric information in a streamlined manner。

 you can do all kinds of cool stuff like this just using our solver off the bat。

But I think more generally， if you're interested in our library。

 DCSM provides a natural framework to implement new sort of hybrid optimization tools that're not necessarily in s or perception。

 so these could be Monte Carlo methods like Monte Carlo research or simulated an ealing or more vanilla research like branch and bound type methods and as I mentioned before。

 this is cool because it enables side by side comparison of different hybrid backend optimization techniques that all can take in the same input。

So I want to maybe in the interest of time，' I'll。I'll quickly go through the sort of last bit of the talk。

 which is about how we develop a semantic sound approach using these techniques and then maybe take questions at the end。

Okay， so how do we apply this to the case of semantic slam or object based slam？啊。

So in the most basic case where we know the correspondence between our measurements， in this case。

 object detections and landmarks in the environment。

 we have a single hypothesis about correspondences for each measurement that our robot has made。

And then in this case， we just need to estimate the robots trajectory， the landmark locations。

 and then the discrete classes of each landmark and just out of the box you can use DCSM to attack problems like this。

But as we saw， assuming data association is correct and known when it's not can lead to navigation failure。

So this is calling back to the first example I showed where object detectors might perform erratly。

 and then what do we do when outliers pop up in our sort of factor graphs？Okay。

 we can relax the assumption of known data association by simply adding a discrete association variable to the problem。

 assuming that we have a reasonable set of candidate landmarks and in DC SAM once again this is easy to do because we can just throw on another discrete state。

 we add it to our factor graph， we write a different factor type that reasons about this sort of ambiguity and we're good to go。

😊，And given that， we can sort of write down this whole semantic slam problem in terms of a hybrid estimation problem where we wanted to find now the most probable set of robot poses。

Semantic landmarks， which could in our case， just consider we consider just a position in 3D space and a semantic class from a known set of classes。

And data association variables， these discrete variables indicating correspondences between each measurement and a landmark in the environment。

And then in this work we're going to use oometry measurements between subsequent robot poses and object detections from stereo camera。

 though the approach that I'm going to describe isn't really restricted to this configuration。

 it's just what we used for this。And the way that this works is that when a new measurement arrives。

 we simply decide whether it corresponds to a new landmark or a new landmark。

 and the way that we do this is using a threshold on the measurement likelihood。

 the probability of this measurement given our map。

 to determine whether this landmark is most likely to be new or previously in our map。

And if it's new it as easy， we just add it to our map。

 we initialize it using the value of the measurement and the class measured from an object detector。

And on the other hand， if we determine that our measurement corresponds to one of the known landmarks。

 there might still be ambiguity as to which of the known landmarks is correct and so in this case rather than selecting the single or most likely association。

 we're going to maintain multiple hypothes。And finally。

 we can account for potential false positives within this framework by just allowing for a null hypothesis decision。

 which just like in the outlier rejection case， this is going to essentially reject the measurement as an outlier and the way that we model this is just as a Gaussian with large variants。

And it turns out that we can play another trick here。

 which is to actually represent these hypotheses implicitly without the need to explicitly keep track of these discrete data association variables。

And so given the set of data association hypotheses。

We can actually marginalize out that association variable to get an equivalent problem defined over only robot poses and landmarks。

 including the landmark position in the class， and so the technical details here aren't tremendously important。

 but the key benefit of this is that we've now dramatically reduced the number of discrete variables that we actually have to keep around in the optimization procedure。

 which is computational convenience。

![](img/06f1a46e5c06b9a5d9f37a2d76644563_2.png)

And now to test this out， we recorded a data set of about 30 minutes of data using an MIT race car ground robot。

 which is equipped with a stereo camera for oometry and for object detections our object detections are sort of simulated we put up around 200 April tag fiduciials at MIT。

And those fiducis allowed us to determine the correct data associations， first of all。

 but also to essentially simulate。Semantic classes。

 and the way that we do this is we take the known identifier of each fidduial and we say you take the identifier number modo2 to simulate a two class semantic samplero。

And in this example， we're also simulating a 10% misclassification rate。

 so 10% of the time we're actually switching the label on the robot。

So it's getting these labels wrong， 10% of the time。

 but that incorrect class is still going into the navigation system。

And we also add additional oometry noise and so on these artificial semantic slime systems our approach。

 which is to depict these two trajectories on the right outperformed the sort of single hypothesis baseline。

 this maximum likelihood method in the center which creates two hallways so might be a little hard to see。

And so this was a little this was pretty encouraging for the application of these sort of ideas。

 so we tried out on some real data and here we're operating on benchmark data from the kitdie data set and here this is maybe not how you'd want your autonomous car to navigate but we're using cars as landmarks for navigation and this can of course be challenging because cars move and we're not actually modeling the dynamics of cars at all so if there happen to be moving cars in the data these end up being modeled as outliers which is kind of an additional challenge to our method。

What you can see is that the maximum likelihood approach quickly fails once even a few incorrect data associations are made。

 and then in contrast， our methods which are on the bottom right in the middle here produce reasonable trajectory estimates even despite noise and detections and a few moving landmarks in this environment。



![](img/06f1a46e5c06b9a5d9f37a2d76644563_4.png)

And finally here's just a more recent version of our system this is all running in DCSM the methods the older videos that I showed were before we moved to using DCSM for everything but this is kind of the nicer version of everything running on a larger kitty oometry sequence and here we're using both cars and trucks to navigate so one of the cool。

Advances that we made when we moved to using DCS for everything was it just became easier to model these sorts of problems with different types of objects and that kind of stuff。

Okay， so just to summarize in this work， I tried to address the question of essentially how to efficiently represent and solve hybrid estimation problems and the specific contributions included a general purpose library for modeling and solving these problems。

 DC SAM， and in turn we developed a new semantic S system that leverages some of these ideas。

I didn't go into it today， really， but our paper on DCSM discusses the issue of incremental inference that I kind of alluded to earlier。

 but didn't go into detail about and also approximate marginal computations。

 which are also provided by our library and actually crucial for getting the sort of semantic slam system that I showed working。

And then the overall technical punchline here is essentially that leveraging problem structure that's exposed by factor graph models is really key to achieving efficient inference and as I was kind of touching on before。

This insight is really more about factor graphs than it is about software。

 right the software tooling is a convenience and it's important from a practitioner's perspective。

 but at the end of the day， the key technical insight is that when we actually model these problems using factor graphs。

 the specific structures that arise in the types of practical perception and navigation problems that we're interested in make it advantageous to consider inference techniques like alternating optimization。

And i'll speak very briefly about sort of future work kind of stuff and ongoing things just some things that I think are kind of interesting i'm happy to comment more about these these are sort of high level but I think some some interesting avenues for future work on these topics would be in developing more expressive hybrid models for perception so this includes things like richer object models that might combine inference over objects shape as well as the category so you know you might know。

From an object classification， if I know that a particular type of object and then I have some limited information about the geometry of that object。

 say from a single view， like if I have a partial view of a chair or something like that。

 but I also have a classification that says that this object is a chair that can actually inform things like the structure of the object that isn't in view。

structure of the parts of the objects that are not in view and you can imagine that trying to write this down in general is maybe a little bit tricky。

 but if you can start to model the individual components， tools like DCM。

Could be useful for elegantly combining these sort of otherwise disparate sources of information。

And the second point is dealing with abstraction and hierarchy so we've already seen a lot of cool work come out recently on the topic of 3D scene graphs。

 you can imagine trying to combine these sort of like hybrid factor graph models with scene graph models。

You know， making decisions like is this a place， is this not a place you could incorporate as sort of discrete states in here in your factor graph This is an interesting thing to think about。

 And then finally， and I think this is like。you know， especially at this particular moment。

 very interesting grounding language models in scene geometry somehow。

 so there's been all of this very exciting work in the context of language models。

And people are starting to think it seems about how we can take advantage of those ideas in the context of perception and mapping。

 navigation， that kind of thing， it could be interesting to think about how these sort of hybrid factor graph tools could be used in that context I don't have very strong ideas or opinions in that space。

 but it seems like something that's worth thinking about。谢谢。And then as a last sort of thought。

 this is based on some recent work from my labmate， Zichi Lu。

Here we're essentially taking some of these ideas about building object based maps and using them actually for self supervised learning。

Or semi supervised learning even bit color so in this case， we're essentially。

Using an off the shelf 60 object pose estimator to build an object level scene map。

By way of robust optimization techniques that do things like reason about outliers， et ceter。

 and then we feed this object level scene map back into the neural network the 60 object pose estimator as training essentially and so leveraging these these。

These object level scene maps we can generate multi essentially multiview consistent what we might call pseudo ground truth labels for robot collected images and then use this as new training data to fine tune the estimator and we found this to be particularly useful for taking an off the shelf object pose estimator that's trained on you know not your data and then fine tuning it for data that you happen to have on hand and this of course can be done nice this is cool because it can be done you know without say a motion capture or without ground truth about the objects you simply run a slam system right so all you need is a camera to do this which is very cool。

And so lastly， I'd just like to acknowledge some of the people who made this work possible。

 including folks who worked on the sort of initial versions of some of this work and then folks who have been working on ongoing versions of this work。

 including David Baxter， Edishshnyweis， Sici Luu， K Singh， Carol Jahoi Fu， Chng Chong Hongong。

 Tony Tran， David Rosen and of course John Leonard， and I thank our sponsors。

 the Office of Naval Research and NSF。And with that， I'll take any questions that folks might have。

 I think we have a good amount of time for questions。Thank you Kevin in。The great talk and ideas。

Can I have a question， hi Kevin。As far as can you go back to the technical stuff。

 the I think the optimization， the slide speaker are you thinking of this slide？Yes。

 so you said that we can use Vi algorithm to solve the first problem because it's this great one yeah yeah。

 and do we have the assumption of Markov do I have the markov for assumption in this in this sub problemm when we're solving the Vta algorithm？

Yeah， so you can see this happening right essentially that when you have a so maybe this is subtle what we have here。

This is I think yeah， many people maybe haven't been exposed to this。

 but but one way of thinking about this conditional subgraph is that you can think of there just being essentially a factor here。

 a factor here， a factor here， a factor here， I don't know if you can see my mouse。

Yeah I can say there and then imagine there's just nothing here there are no continuous states anymore。

 but but all of these edges have just been replaced by a single factor。

And that is exactly what a hidden Markov model would look like right a discrete factor graph with a factor on each of these nodes and then a factor node attached to each of these nodes and then a factor node linking each of these nodes and so that's exactly what's going on sort of I guess。

You could think of there being a maybe an implied sort of Markov behavior going on， right。

 that this state here is conditionally independent of this state here on this first state given this intermediary state。

Okay， so why if there are some dependency of previous several steps can we can we solve that problem or do we have a silver for that kind of problem Yes that's a wonderful question so so getting back to what I was saying about sort of when our method is efficient if you have that type of multi I don't know the great way to maybe nonmark off as the right way to describe it that type of dependency across multiple states you can still solve that problem using our method our method in uses max product elimination to solve this discrete subproblem yeah the caveat being if this。

Dcrete subgraph is complicated。We make no promises about when you're going to get a solution right so if this is a particularly complicated discrete subgraph max product elimination is in general an exponential time and so because we are actually trying to solve for the optimal assignment to discrete states condition on continuous states you may be waiting a while for more complicated discrete factor graph apologies。

 it happens that this was enough for the types of cases that we are interested in， for example。

 semantic slam outlier rejection， all of these cases break up in a nice enough way that we don't have to worry about the fact that we're using technically an exact inference method for discrete optimization here or for the discrete factor graph subproblem。

But if you have a more complicated topology and you're concerned about time。

 which you probably would be in that case。As I kind of mentioned。

 you can swap out Max product elimination for a different technique like coordinate a sense say。

 for discrete states that is more computationally efficient Okay yeah， thank you I。

Of course then you might be sacrificing things in terms of performance。

 but what can you do you know in the context of some of those problems they're incredibly computationally challenging to solve so you have a question in chat not sure if it's for Ellon Musk or you。

 but you can try how do you。How do you think Hesla's peer region driver assistance system that relies entirely on the camera what do you think about it and that's an interesting question。

I don't have strong opinions about it。I guess。I guess is the is the。Question。

 whether or not I think that's a good idea or。I。I don't think I don't have a strong opinion about it。

Probably you could say maybe I can reframe the question， do you think the vision only system？嗯。

I is a good solution because the sense of factor graph and what we cover in basically robot perception is the multis of fusion right I see actually tendencydency of the sensory input and the robots yeah yeah that's that's a that's a good point yeah so certainly I think。

那么。From a sort of engineering standpoint， I think redundancy is good， I think。

It's good to combine information。From multiple sources。

 you know from multiple sensors where possible。The details about how that happens are always challenging。

 but I think if we can figure it out， it's probably worthwhile as opposed to relying on a single sensing modality。

Do I have a question about these variables？But the discrete variable is always binary or they can be any integer Yeah that's a great question so yeah in the semantic slam case like。

I know I like I I only talked about two classes in our semantic slam experiments we've done we've done things with more than two classes。

 especially using the April tags in this sort of like simulated example that I showed it's very easy to model different numbers of classes and we've done this so so in our software I mean I would say both algorithmically in terms of the math and then also in the actual implementation there's there's nothing that's constraining you to deal with specifically binary variables versus you know any other。



![](img/06f1a46e5c06b9a5d9f37a2d76644563_6.png)

Type of discrete state。And a follow up question， how bad can we initialize these categories。

 essentially if you make it random， it will be basically unsupervised， does it work？呃。

Not necessarily so to give I don't have a good I don't have a good picture for this。

 but it would be so an example of how that might show up is if you were to say initialize like if you initialize like a robust s problem and you take a whole bunch of the outliers and you initialize them and you say all of these outliers are actually inlier measurements then you're giving you're essentially just going to end up with a horrendous initial guess right and it seems very likely。



![](img/06f1a46e5c06b9a5d9f37a2d76644563_8.png)

Like even even in the case where you。Even in I would say like traditional s applications。

 if you start with a poorer initial guess like that， you're not guaranteed to get good solutions。

 I would imagine that if you did something if you started with say random discrete variables in this case that would be pretty bad what we usually do is not initialize the discrete states though because we solve the discrete problem because we're using max product elimination to solve the discrete problem we're getting an optimal solution to this conditional subproble so we actually don't have to initialize in our in this specific case we don't have to initialize the discrete states at all what we do instead is we initialize the continuous states and this is typically。

You know，I'll say this with an asterisk， this is typically much easier because we can initialize the continuous states from something like autometric estimates or something like that。

Ands。As long as that initial guess for the continuous states is relatively good。

 we can bootstrap this discrete solve process。And obtain good solutions。 Of course， if you。Have。

 you know if a substantial portion of your measurements。A corrupted by outliers。

 this can be very hard to do if if you like a good example of a case where this is particularly tricky is in the case of like multiple robots where you're trying to reason about inliers and outliers in loop closures between different robots and you have no common reference frame for these robots otherwise right this is like a challenge that's addressed by like paraed consistent measurement maximization and things like that。

 but the issue here is that we don't have an initial guess for each of the robots trajectories in a common reference frame。

And so it's very hard to bootstrap the DC Sam optimization process there but what you can do and this is something that I think is very exciting。

 I don't know that I've talked to anyone really I've like publicly about this before or anything like that。

 but I think it'd be a really cool idea to initialize the the DC SAM optimization procedure using something like paraized consistent measurement maximization that you can use to give an initial set of discrete assignments to then solve the continuous states and then that gives you a way to bootstrap this whole process which is sort of which doesn't depend on say like having a common initialization for multiple robots in the same sorry an initialization for multiple robots in a common reference screen。

So here's now that's very interesting， here's another idea based on what you question based on there。

Three， so when you present this discrete layer， it immediately makes me think of。

Well while you stop or you can just make a decision tree and top of this continuous variables right and the moment you have the decision tree。

Maybe you're thinking about something like branch and Bo or something that you can globally actually search。

 it does not have to be real time， it does not have to be synchronized with a continuous part。

 but as you move forward you can continue the search for the most promising region。Solved。

 so which is， you know， the go ICP， for example， that's what they do。 So I wonder if you。

T about that the problem is you have to give up efficiency usually they're very slow right but the conditional independence here might add something yeah and there that's that's a good point and and it's worth calling out you know methods that that are kind of going in that direction like MHM2 being one of them that that tries to sort of simultaneously leverage things like the conditional independence structure of the factor graph and a sort of pruning based procedure for exploring all the sort of discrete hypotheses but then also。

I should mention IMHS incremental multi hypothesispothesis smoothing which is work that was applied for this gate estimation problem and I think there's ongoing work to get this sort of method into GTSM so there's definitely folks who are working on on exploring those types of approaches I think it'd be cool to you know。

I don't know that we know exactly right now what the right。What what will be。

 there are so many possible variants of these types of approaches， what I'll say。

 and I don't think we have。Great direction in terms of identifying the best possible things to explore it now。

 because you can imagine。All kinds of ways of combining。you know。

 a branching search procedure with a local optimization procedure like the one that we you employ here。

 and you can play all kinds of games with scheduling the you know how you perform different types of optimization on what time horizon are you optimizing different sets of variables。

I think there's a lot of room to just explore different ways of doing that and perhaps it'll be problem dependent at the end of the day that people could find different variants of these techniques that are specialized to particular tasks。

 but I think the nice thing， like I said from maybe a high levell sort of practical perspective。

 is just the availability of tooling to encode these sorts of problems。

 I think is a useful first step in that direction。Yeah， I definitely agree with that。

Have more questions from the audience。Do you label features for each landmark or just use bounding box of landmarks Yeah that's a good question。

Yeah， I didn't mention this I think I just forgot to mention this。

 but in the context of our semantic slam so this is regarding our specific semantic slam system and the way that this works is that our so what we end up doing in the system that that I showed is we。

Get an estimate of the position of each landmark， like say a car here as the point。

The median depth point that falls in this bounding box and the XY position is just given by the center point of the bounding box so this is a very coarse way of estimating object locations。

We didn't need anything， I think to demonstrate this work。

 we weren't trying to do anything sort of fancy with this， but in the very beginning of the deck。

 I kind of showed a sort of illustration that motivates a sort of alternative approach。

 which is here。Which is that we could actually use key points that are annotated with semantic classes and we haven't tried this。

 but it's a very cool idea it would slot very nicely into this sort of framework there's no different There would be no you know effectively no。

No change to the overall formulation。At a high level at least and that would be a cool thing to try like you know。

 if you had a segmentation say。That would be cool， but to maybe concretely answer the question。

 we use the bounding box and then from that we extract the center point and the median depth of all of the points from the stereo camera that live in that bounding box and that gives us our estimate of the object location and the class just again comes from the detector。

See any more question， maybe one more if anybody has any questions。All right， thanks。Very much。

 Kevin。It's great to hear from your work and look forward to the next packed Philip of Boston dynamics next time we will have perception probably maybe online perception this time for sure yeah。



![](img/06f1a46e5c06b9a5d9f37a2d76644563_10.png)

Thank you very much。close decision， awesomesome， thanks so much。

