# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p19 -19-Lecture 19-SLAM I.zh_en -BV1UfAmeUE3e_p19-

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_0.png)

Welcome to the first lecture on simultaneous localization and mapping。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_2.png)

We built so much in this course so we can talk about。Freely about s。

 Slam stands for Simultaneous localization and mapping。We。

Learned how to do a state estimation using a range of filters that we covered。

We saw them as instances of。Each of them was an instance of。

Base filter in the narrative that we built。Typically。

That filter consists of a prediction step and a correction step。

 And then we moved into the optimization。 We talked about how to do frame to frame alignment of。

Images， RGBD images and point cloud。We use particle of fielding for localization in particular。

 And then we talked about some mapping algorithms。 today。 We want to put everything。

In one framework and talk about how to do both localization and mapping at the same time to do localization。

 we need a map。To do mapping， we need localization。In Islam， neither of them。Is given to us。

 So we want to build a model of the environment， the map。While we are localizing。

 we respect to some initial frame that we decide。As time moves forward。In this particular lecture。

 we will focus on graphiclab。Historically， there are three。Main paradigms of Islam in the literature。

The problem initially started。By looking into。Comalman filtering based the s and its variance information filter。

 sparse extended information filter。Those were categories of。

Slam methods that we're using filtering based method。 And as we discussed in the filtering。Methods。

 we marginalize past information every time we predict。

 we marginalize in the base rule so we don't keep the history。 we only estimate the latest。

 let's say， robot pose。So one particular problem in common filtering basedlam is that we need to work with landmarks。

And every time when we track a set of landmarks as our map in this state。

We need to solve a data association problem。Meaning。

 we need to know what are the correspondences between sort of observed landmarks and the map。

We maintain in the state。Typically， landmarks might not come with signature that we know correspondences。

 so we need to do some sort of a statistical test to find out what are the correspondences。

 and that process is prone to outliers and mistake。

And the filtering process is not very forgiving for such mistakes， because if you make a mistake。

 you inject outliers and we never go back in time to correct past mistakes。 We only linearize once。

 incorporatepo information and move on。 So in that sense。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_4.png)

It's a framework that does not allow for dealing with outliers of。A rising firm data association。

Then part of the filtering came along， fast Islam is a version of that。

That we build a map can be occupancy grid map or landmark maps。

 And each particle is a hypothesis for the robot pose， and we track。A separate map for each particle。

This method works well， and still some。Versions of it called G mapping， for example。

 or Fast Islam algorithms。Are in use for 2D robots moving and indoors digitally。However， a problem。

We face here is the scalability problem。On top of that， typically。

 particle filters are also within the filtering class， although they can be implemented as smoothing。

 but that will make them only more expensive。 So tracking multiple hypothesises and track building a world model for every particle。

Becomes。Quickly， intractable。So in practice， we might end up using a few particles for。

Solving the problem。Then the next generation of these methods was to use to move on to a smoothing framework。

And that was motivated by the fact that this s problem admits a particular structure that makes a problem a sparse。

 even though it's larger scale， we keep a lot of data history as the robot navigates through the environment。

But。The problem ends up being a sparse linear systems that we wish to solve。

So it was counterintuitive that if you。Get rid of the history。 It makes the problem harder to solve。

 If you keep the history， although you're dealing with more data。

 but it makes it easier to solve because we enjoy the sparse structure of the s。

 This was discovered in a iconic paper。 It's called a sparse。

 Ex a sparse extended information filter。😊，That won an award in transaction on robotics。

 that was in the context of extended information filter and the observation was that if we keep robot poses and connect these poses across time by establishing some constraint。

 then we see as spa as the structure。Now， when we go to graphical models。

 we see that explicitly already in the Jacobkkuian that we construct for the listed squares problem。

So today's the main paradigm for Islam is Gr is。Right， so the other two are history。

 and we're gonna to focus on Islam。Tomorrow， we don't know。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_6.png)

Maybe there will be other methods。So the graphical models for Islam。

 it means that we use techniques in。The context of probabilistic graphical modeling to formulate the problem。

Although there are many ways to。Perform inference。In a graphical model。

We make a particular assumption that the noise is Gaussian。

 and that will lead to at least a square problem。So we will not look into a general inference methods and graphical model。

 It is possible， but that will not give us。Solvers that can operate really fast by solving。

 this is the worst problem。As we discussed， list squares is a problem for solving it。

Over theter system of equations， we have more observations than the number of variables。

 which makes our matrix tall and full full column rank。We discussed this in the optimization lecture。

And then we're going to apply。This formulation to our s problem and solved it using Lisa squares。

 So the problem is how to formulate the problem。 Once it's a least square problem。

 I expects you to know。What you do at that point？

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_8.png)

So how to formulate a problem？Imagine a robot is navigating。Through an environment。If we。

Record robot poses at discrete timer steps。Then you might label them using these blue triangles。

Then you can think about temporal constraints between any robot two robot。

Pooses that we wish to track。And this。Way of tracking the robot pose will give us， of course。

 a discrete time trajectory of the robot。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_10.png)

For example， you can call this。You'll node at time T 0， T 1， T 2， and so on。

 So this will be a trajectory。What are the examples of this constraint that we can add？

Based on everything you learned so far， how can we establish？A constraint。Between two robot poses at。

Two consecutiveative time steps。A transformation， where does it come from？Poses。Well。

 where does it come from， We need a sensing。Mettter to get that post。 You're right。

 It's nice to have maybe a pose， right。😊，2D or 3D。But where do you get it？No。我。Odoometry。

Using maybe real encoders or。What about IMU？要这。Could be IMU， could be wheel encoders。

Can we use cameras？We learn RGBD visual autoometry could be from camera。

Could be from ICP could be point cloud registration。So in general， it can come from a variety。

Of sensing modalities。 And that makes it compelling because now we're talking about a generic framework for sensor fusion。

We can combine heterogeneous types of sensors。Byy different techniques of registration into one framework vote for a state estimation。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_12.png)

So although it's an abstract idea， but you do have a specific。Knowledge how to get such constraints。

Now， if you just rely on temporal constraints。The robot will eventually drift。

Imagine every time that you are。Using wheel encoder to accumulate。Delta pose between two nodes。

 or every time you register two RGBD images。Maybe there is a small error，Very likely。

 So unlikely you get the perfect solution in practice。

The accumulation of all of these small arrow over time will be a large drift。

 So the robot will necessarily drift。However， if you can revisit， for example。

 the robot is coming back。To the same area， if you have a way to recognize and establish constraints between previously visited areas or nodes in the graph。

We get a special type of。Constraints。These are not constraints that are。Temporly sequential。

These are called。Loop closures。As you see， the robot is closing a loop， loop closures。

Add information that we need for removing the drift from the trajectory。

The more constraints you add to this graph， the more likely we。Have a better answer。

 theoreticaloretically， that's the case。 In practice， of course， we need to be careful， maybe。

Snoisy outliers。Local minimum for the sal， all of them。Initialization issues。

 these are problems in practice， but theoretically， more information， more edges。

To make the graph more connected， it should be better。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_14.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_15.png)

Although there are research showing that there are diminishing return in how many。

Edgeges you want to add theoretically again， it's better to add more。

 but at some point there is a diminishing return as well。

There's a structure in this graph it's called that。Amin a sub modular。Information gain。

That's part of the research in Islam and it's possible to select a subset that you have some minimal loss。

Of information。That's just a side note。So the idea is that you build a graph。

 you imagine how the robot or your sensor is moving in the environment。

And represent the problem as a graph。And this graph is abstract enough that we can。

Show different types of robots and sensors using just nodes and edges。So every note。

Consponds to your variable that。Can be the robot pose or can contain the velocity of the robot or bias variables。

 In general， that's your the node represents your state variable。The edge。

Is some sort of constraints between the state variables。

If you remember from how we formulated the RGBD registration。That's one type of edge。

 It's a measurement model that links to。Poseses to each other through some measurements。

So the core idea is that build a graph by establishing these connections。Then， formulate。

A problem by minimizing the error between。The estimated variables and observations。

Then by minimizing them， we should recover the entire trajectory。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_17.png)

For example。Imagine a robot is navigating in this 2D environment。If you use oometry， for example。

 to build an occupancy grid map， you might expect to get something like this which is not very useful。

 The map is inconsistent， as you can see。All the walls are overlaying on your shut and it's not very useful for navigation。

Now， as the robot is navigating， we construct the graph。

There are potentially many nodes along the way， connected biodimetry。

And as the robot is reobserving same areas we see， we have a lot of。Loop closures。

 these are connections that the robot is establishing in this case， using a 2D laser range finder。

By registering observed point clouds and previous time steps。And the current time。

So once you build this graph with many edges。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_19.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_20.png)

This is the graphical representation of the problem。

 which is exactly what you've been working on in your homework 7。

The Intel data so that you're processing is something that is built just like this。However。

 the raw data is processed。 You are using processed。Data that was used in some front end。

 you're working on the back end part when you are given all these constraints and notes。

So there's a part of the problem that。What solved for you in your assignment？



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_22.png)

Now， ideally， when we solve the problem， we expect the trajectory to go back to its consistent form。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_24.png)

When you have this trajectory， then you can use this trajectory to build the map。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_26.png)

And then hopefully that map is consistent。So although it's simultaneous localization and mapping。

The idea of map is。Very abstract and somewhat vague because there's a lot of freedom whether you're actually building the map at the same time。

You optimize the trajectory or you're using a map representation that is built after solving the localization problem。

We will talk more about different types of mapping， but in this case， it's a pose graph。

 so the pose graph。Which is a particular time type of Islam。 Well， where all the constraints are。

Relative measurements between robot poses and all the nodes are robot poses。

It solves the localization problem。 All the map information is converted into post post constraints。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_28.png)

So the current theme or narrative that you see in graph islam in literature。In the most abstract way。

 you can present it like this。Typically， we receive raw data from sensors。

The raw data can come in form of point clouds， IMU signals， wheel encoders。Monnocularcular images。

 RGBD images， and so on。There is a front end， the front end is responsible for constructing the graph。

There's no unique way， depending on the sensor or data that you process or how you want to combine them to get better constraints。

 you might you might come up with different ways of formulating the problem and that that is precisely。

The topic of research of many papers you see， different ways of realizing this framework or processing data or inventing new factors or measuring models for the back end is the topic that people still publish on it。

Once the front end gives you edges and notes。Then。The backend is typically just responsible for graph optimization。

So there is a need for an inference。Method in the back end。

Optimization methods by the assumption that we will make are very attractive because makes it very fast and we can run it online。

However， there are other possibilities as well， you can always look into broader context of inferencing graphical models。

And they should be applicable。Although， as far as we understand。We cannot make them real time。

For any interesting problem that we want to solve。For robotics。So what does this mean？Now。

 by the way， the interplay between front end and backend is not super clear here that whether the backend is communicating some data to the front end or not。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_30.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_31.png)

These are all up to debate。Whether it should be like that。

 ideally all the modules will communicate and they are integrated。But to what extent that's possible。

You need to look into different ideas and see what's the best practice at any time。

In the simplest way， of course， they're disconnected。

 The front end builds the graph passes to front end。 You optimize something。

 and then you might use the trajectory。To do some initialization in the front end。

But that's not never revisited。In the sense of regenerating those constraints in the graph again。

 right？Imagine you also want to go back in time and redo some of the work that Fronend did。

 that's more unusual to see in the literature。So this interplay is not well defined。

And it's part of basically problem solving。To get constraints that you can think about two main。

Approaches， one is that to use。For example， if it's in the context of point cloud registration。

 you might want to use。We must resend point cloud we observe from the sensor with another point cloud observed by the sensor。

In the past， so that will be just frame to frame registration。Or maybe you are building a map。

 and then you want to use the map model as your world and register the most recent。Frame to the map。

So this is another idea because now I'm using the reconstructed scene or the map。

Whatever representation you might have。To guide my。

Problem solving in the sense that I want to find out new constraints in the graph by building on the partial model that I have at any time。

Now， this ideas tends to。Work better。Frame to map registration。 However。

 it comes with challenges in practice。 framera to map registration is not always。Easier。

 depending on what method that you're working with， for example， for point cloud registration。

 your point cloud from the sensor might have。A different density from。Your map。

Whichch is the accumulation of multiple frames。And many point registration algorithms cannot deal with that。

You might need different tuning， different parameters and so on。So it's a good idea， but in practice。

 it's not guaranteed。To give you a better solution。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_33.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_34.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_35.png)

So everybody is comfortable with this narrative of front and backend。Constructionally。

Like it seems that got construction will。公都没 to他这게把。Through its environment。

 even about the chaing from the ground optimization， that happens after or may not be connected。So。

 I guess。Can you explain a bit why the not part。这个话只有担。You're asking if the robot can navigate。

Without having the map。Right， because in the， I guess data set that you showed us like the photography soldiers are lot in that data set。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_37.png)

Good question。So you're asking if I need to solve a s to have this map so that I can navigate。

How can the robot move around to。Collect data to begin with。That's a very good observation。

So the data is collected by deriving the robot manually。 This problem is not active。

 The problem of a state estimation or perception。It is passive。

 the motion commands are given in this case， for example， you are driving the robot around this room。

 you collect data， maybe offline， you process it to reconstruct the scene and solve the localization problem。

Or even if it's online， you are driving the robot， so the robot is not autonomous。

Which is less exciting。 obviously， So if the robot now is going to be autonomous， that means。

It needs to make decisions for acting。There is no manual intervention for moving the robot。

 In that case， the problem becomes active， and that might be known as active localization。

 active mapping， active Islam。Exploration for mapping and many other names。

So the problem is active when you have control over actuation。In that case， you do need。

A lot more to help the robot to move around， for example。You might want to build a local map。

 depending on what is your exploration algorithm， you might need to know the global knowledge of the environment at any time or at least partial knowledge of the environment with global localization。

 or you might just rely on local information to move around。The early algorithms they， for example。

 wall following， right， find a wall， just move along the wall。Hope for the best， right， Obviously。

 the robot doesn't know where it's going。But that allows you to explore。In some sense。

And maybe it might not be a bad idea for some initial phase of the exploration。

Another idea is that build start here， build a map。

 we can build it without moving because your sensor is seeing some areas near the robot。

There's a method called frontier based exploration。

 Find the boundaries between these known part of the maps and gray area unknown。

Then the robot knows that if， if it moves to the boundary。It can expand a map。

So maybe choose the nearest one。 That's the nearest frontier exploration。Thema basic standard。

Autonomous exploration method。However， as you move。

 you notice already that you need to maintain good localization。

 so you expand the map and keep the map consistent because if've at any time。

The robot localization becomes inaccurate， or for example， you detect the loop closure now。

 the slam fixes the graph。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_39.png)

From。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_41.png)

This for this。Whatever map you were tracking and locally you were trying to plan is not validd anymore。

 So you need to。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_43.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_44.png)

Rebuild the map。And it is a problem。 How do you know when to rebuild the map。Doing。

 redoing everything from this Christ is very expensive。

Partially updating it might not be easy because。The statistical algorithm we had。

Was not allowing us for a flexible structure to update and down the map necessarily， right。

So each of these problems are challenges in practice。There are some work in literature on that， but。

There's no。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_46.png)

Answer that know， ends the problem as a solution。 There are good ideas in literature。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_48.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_49.png)

So in this case， the problem is passive， somebody is moving the robot。

Which is the same assumption in localization。 The control actions were deterministic and given。

We never assume we have control over them。Does that answer your。

Question so the trajectory is a sequence of。Robot poseses。Expon。XN。For example， here you might。

You might assume。X， I is in S， E2。If it's a 2D robot。

 you have 2D position and orientation of the robot。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_51.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_52.png)

Now， as the robot moves in the environment， you have。An o constraint between node I and i plus1。

Maybe from the wheel encoder， you know。Your。Delta x， Dlta y， Delta Theta movement。

And then that will give you an S2 constraint in the graph。So you could basically。

Put this in S E2 matrix。 And that will give you。A measurement。

As we ci in the postgraph example in the optimization lecture。This is a temporal constraint。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_54.png)

Right between I and I plus one。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_56.png)

To establish a nontemporal constraint， can we still use。Aometry， can we。

Rely on tracking of the robot。Yes。😊，No。正し？No， regardless of the drift can be established。

Non temporaloral constraints by just tracking the robot。

You can by just attracting like three sense liketry we just give thistry， I'm walking。

 I'm counting my steps。Can I establish a constraint between history？From what I observe now。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_58.png)

No。It's not possible， right。Because the images I see。

 let's say I'm solving visual autoometry I'm walking。I can track a additional step using vision。

That's one relative pose。I can count the steps， that's another constraint。

 which is whether there is no limit， you can have many omi constraints。Between two nodes。

But to have some sort of evidence。That what is the relationship between my post here and 1 steps ahead here？

I need to look back in time。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_60.png)

Whether that's a map or the exact image I observed to establish some sort of evidence based constraint。

And that evidence based might come from a constraint between， for example， two images， right。

 maybe are you stored。We're all measurements， then I look back in time。

 try to establish a constraint。Or maybe I'm tracking a map。Based on where I am。

 I try to establish constraints nearby。So this is not a problem that we can solve with using temporal data。

In particular， a time is step I。We might have observed a point cloud。

A measurement of a corner of a room that's like this。And a time of step J。Maybe I observed。

The same corner， right， Maybe the robot moved around the room， came back。To the same corner。Now。

 this node I X， I and X， J are not the same place， right， maybe X。Jay is here。However。

 the sensor is observing the same area。 There must be a relationship between these two。

Given the overlap in。The sensing。So that's the goal。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_62.png)

For example， I can use here， I can use point cloud registration。 Maybe I use ICP。To register。

These 2 D point clouds， that will give me a relative pose。 That's the constraint between Xi and X J。

So conceptually， this is how we get。Loop closures。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_64.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_65.png)

And in practice。So the autoometry the way it's related to nodes because Xi is my state variable。

 I want to estimate it。X I plus1 is also my state variable。 I want to estimate it。The edge。

Is some sort of measurement you？The way they are related is that X inverse times Xi plus 1 is the relative movement。

Given X I and X I plus one。So if I have this relative movement movement from any sensor whether I am U。

 wheel encoder， onclo camera。This constraint is true。It must satisfy this relationship to the graph。

That is exactly my measurement model or factor model。When。

It's observation based is not coming from temporal tracking。

In the context of having a state variable as poses， it's the same thing。

 except we're not talking about I and I plus  one， you see I and J。

 J can be any other node in the graph。So that's the difference。You might say， okay， this is。My。

 I'm gonna show it with Z。Maybe you get this from。A camera， maybe you extract features in two images。

 you run Rasack， you find a transformation。That will give you the Z， the relative transformation。

So based on observation evidence， you generate this constraint。Because the censor doesn't lie。

But we do not know the value of these variables。Then we formulate an optimization problem based on sensor data。

We find a trajectory that minimizes some notion of error。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_67.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_68.png)

You don't get any observation edges we have M1 edges。

Our slam devolves to like the same performance as another s solving solution。

 like when you don't get any loop closure， is it the same theoretical？F filter or something else。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_70.png)

That's a good question。I'm going to use this as slide because we have plenty of white space。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_72.png)

The question is。If we never get any loop closure。Is this the same as column filter？It is not。

It's not as good as a s because this is still a dormitory。But it's a dorm in the sense of。Smoothing。

 I am still trying to use temporal constraints to track the robot。 So in the sense of oometry。

 it's a better way of doing oometry。And you might choose to do it over a window。

 so it's a window tracking。The filtering。We never。Let's say column filter or。Partig your filter。

We marginalize。The history。We only estimate the latest one in the prediction stage of base filter。

 we integrate out。Now that integral is not something in close form we have a universal solution to it for carbon filter。

 given the Gaussian distribution， we ended up having that。

Update for the prediction and the covariance update。For particleig filter， we were just sampling。

It wasn't even a parametric calculation。Nevertheless。

 we only we are concerned with this latest valuable in filtering。Whereas in smoothing。

 we look at the history。So in this framework， maybe this answers your question。

 you do get what you were getting out of common filter。If done correctly and carefully。

 you can cover that case as well。The general graphical model can model something like a column filter as well。

 okay。Now， when I say graphically it so that you need to be careful about the geometry， right。

 because you never see something like。A lead group treatment of graphical models for inference in common filter that comes from completely different literature。

But it is possible to unify them。Once you realize it correctly using techniques we learned here。

In the linear case， it's very easy， linear column filter， it's just in your homework。

 you had that it gives you the same answer as。Maximal posti and linear list square。

You could do recurs civil listed square。 It will give you the same answer。 in the nonlinear case。

 it's hard to say because。Keep the history that will affect each other。Get rid of the history。

 If you didn't do your best at the time of linearization， obviously， we lost something。Right。

This couple slide。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_74.png)

We have Xj and x5。The question is， what if the loop closure is wrong？

We somehow fall into trapmp of outliers and establish a wrong loop closure。Now， that is。In this case。

 we're talking about the constant， right， That will be the next step。 Now。

 you want to solve it in practice， you have to deal with outliers。That is a problem in general。

Because if the system is not robust， it will break down easily when you add outli。

Just like the linear regression example I gave you when you had outliers。In the context of。

Cman filtering， by default， the filter is not robust to such outliers。If you do wrong association。

 that can cause divergence。In the extreme cases。In the context of optimization， we have more options。

Maybe when we formulaly the least of squares， we turned it into an m estimator。

We talked about wrapping the。Residual norm of the residual of the least square problem around a robust kernel like kshi loss function。

Right。You remember the idea of。Having a quadratic。Lo师。And then you。

Use a robust kernel to bend down the size of the quadratic model。We have more options here。

That's exactly what we do。Then we are。Robust to outliers， to some extent。

We can tolerate some outliers。Now question is， can we detect outliers and get rid of them？Maybe有。

It is possible theoretically， in practice it depends on what type of inference you're using。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_76.png)

The generally topic on outlier detection is is still an ongoing。Debate。

But it is possible to separate the process data into inliers and outliers。

 If you can detect outliers。Itch is a binary label， right， by definition。

 what something that is outlier is not an inlier。If you can delabel them and detect them。

 then you can exclude them。However， how much overhead that process will add to your problem。

 That's the question。If you go after， let's say， a typical optimization formulation。

 that will end up being a mixed integer program。Which is expensive to solve。

 You're not going to have real time Islam。By solving a mixed integer program。

You might want to do Bayesian inference。 You can do variational inference for。

Defining some latent variables to label outliers。 again， that makes it expensive， right。

If you can do that and do it fast。You should be rich。😀呵。😊，So we won't label them as outliers。

 We just make the list of squares robust。 right I'm telling you about the standard way。

 There are fancier ways to， again， always build on these algorithms。

We should always start from this standard。Methods that form the core of them。

The scene is associated with some existing。Map all previous images of frame， two options。Right。

That's another good question that I was waiting for it is that。Well， in theory， it makes sense that。

To go ahead and establish loop closures。And everybody is happy。 But in practice。

Where to start the set。There are so many previous nodes and history。

 You might have thousands of nodes， and。Locations in the map that you can look for establishing loop closures。

 just searching for every frame to find all possible loop closures that's combinatorial。

 and that will exponentially grow。So that's a big problem in practice。That's why。

 that's where a map come in。 If you have a map and you know roughly where you are。

 maybe you limit your search to that neighborhood。You have to make some sort of decisions based on sensors。

 the range， the type of problem you're dealing with， right， There are tuning and。

Design choices of that neighborhood。That you want to search if you have higher level information。

 semantic knowledge usually help with data association。Right， if you。For example。

 have some notion of black white segmentation of some outdoor area。And from your image。

 you know what area region you are in right or indoor， for example， you know this is a classroom。

And in your map， you have classrooms。 you're not going to try to establish a constraint with the cafe and the classroom。

So this higher level of information in form of semantic abstraction can help with that a lot too。

Make the session more efficient。So this is work direct。つれた。Po，But whatever is。

 it's an entire group and you come around with here。What if we。Now， the question is。

 what if we come back to the initial post after a long time？That's the biggest loop you can close。

It's the best loop。That's really good because now you go after a long time。

 large loops are better than small loops。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_78.png)

Maybe I can point out that。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_80.png)

Again， all of them， if they become different instances of the same framework， but。Generally speaking。

 instead of temporal frame。Maybe you have some landmarks as well， right。

You keep reobserving these landmarks。Now， but its still you're operating in a window。

This is a still oometry， although you have local the closures。So， the local loop closures。

It's a look closure because two different poses observe the same landmark。

We're not going through calculations of them， but you can always。

Convert them into post post const geometrically is possible。So the local loop closures you see here。

 it will certainly help to improve this local tracking。But to really。

Have a food slam system is that when you go after a long time。You really need to look like this。

You go around a building， you come back to the same spot and you establish this large loop closure。

That's where we expect to enforce。More consistency into reconstruction。Without that。

 you might still expect some drift。Right。Because even as small， why is that， Because well。

 you do well in local window。But it still。Unless if you do perfectly。There is a tiny error。

And different windows with tiny errors。You really need this large loop to get rid of those tiny  errorss getting accumulated across time。

 right， It is impossible to do perfectly in practice using noisy。Data。Right。Does that answer your。

Question。Kind of。Which part of it is not answered？My question was。If you come back。

There could be so much that if you。Okay， that's a good question too so now the question is that is that's important。

If I'm relying on my current estimate to search a nearby in the graph for loop closure。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_82.png)

And it's taking a really long time to go around the building and come back。

 If the drift is so high that。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_84.png)

This node is not falling into the neighborhood of。This note， right。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_86.png)

What can I do？Now， that is a problem if you only rely on。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_88.png)

Your estimate for detecting loop closure， which is why some papers do that。

 although they get success successfully， they get really good results on some data set。

 But it's generally not a sufficient idea。 You do need a way to detect loop closures without relying on。

Your estimates。Visual place recognitions help with that。

And they can solve the problem because if visually， you recognize that this is the same place。

You first detect it， and then you go ahead to establish some geometric relationship。

So the detection is somewhat independent of。Your current guess。

 because it's a visual context you see in the image one。Successful method is。Bag of wars。

 right bag of。Visual words， so you convert each image to a histogram。A visual word。

 And then you make a library of them。 And then you for every new image。

 you compare it against the library to see which of the previous images matched that。

 if it's a match。You are seeing the same area from a different possibly view。

Then you can try to establish。A geometric relationship between node that。Crespond to those images。

 right？It's a very， very good point and that is a big problem in practice。

So you have a lecture by a dissertation by Cynthia from last year on visual place recognitions on Can。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_90.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_91.png)

All right， so let's formalize it a little bit。I think now you're comfortable with the idea of graph。

 node， edges。Look closures。There are different ways to。Build that graph。The graph can be directed。

 The graph can be under undirected。One particular choice。That is very convenient for modeling。

 in graphical model is called a factor graph。We build the example。

 and then we say what is a factor graph。You have your robot here。

And then you have the landmark in the environment。 Supp you have。Your camera can detect the object。

 and it will tell you。2D or 3D position of this landmark。So the measurement model。

 the constraint that you can add。Within the robot， your sensor and the robot and the and the chair。

We show it using this。Model。You can use circle， or you can also use。Square， there's no difference。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_93.png)

AndYou can use a variety of sensors for these constraints。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_95.png)

Now the robot moves， thedimetry will give you another type of measurements。

And we gonna visualize it again。Using a model。There's another landmark， the robot moves again。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_97.png)

Now you see the same land north again and again as you move。Forward in the environment。Now。

 at this point， this is a graph where it's a particular type of graph。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_99.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_100.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_101.png)

Because。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_103.png)

Now， you can see that all the table and chair and。We can't visualize all the possible landmarks。

 right。 So we abstracted in the graph as these nodes。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_105.png)

So the nodes are the same。 The color is just to show you that greens are landmarks here。

You don't have to use different colors。And the purple notes are the robot poses。All the edges。

Are called factors。 These factors are measurement models。To make it more concrete for us。

 every measurement model is the residual in the listed of square problem that we defined。

It is a relationship between these variables and your measurement。And this is called a factor graph。

It is called a bipartite graph because you can partition the graph into two parts。

 one part are the nodes。The variables。And the other parts are the factors， the measurements。The fact。

And a notes。Now， is there any limitation what type of factors I can add to this problem？No。

The state end some sort of bear。Better rest of your trajectory than not did。

So as long as I can come up with a way to use that sensory data to establish a relationship and model and define that residual between my state variables。

I'm good to use it， so I can add virtually unlimited amount of information to this graph。

To improve my estate estimation。So it's a very powerful framework for fusing or combining information from multiple sensors。

However， it is model based， right， so we require model for a sensor to describe the relationship between the variables。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_107.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_108.png)

What about loop closures？Likewise， loop closures are just constraints between non temporal nodes。

As you can see here。Maybe we use。Cameras to detect loop closure between nodes that are far apart using maybe。

Visual place recognition。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_110.png)

So that's all you need to do for formulating your slam problem graphically。 Once you have this。

 what type of information you can read from this。It's important you， you。You're able to read this。

Is there anything confusing here when you try to read the graph？你盒子我不死。り増えて。啊，这边是。It the sense。

Question is， when you close the loop， using landmark information。Or not。We can。

 There is no limitation， so you can。Maybe again， maybe that was the example of pointcl registration。

That will give you directly post post contrain。Or maybe you are observing the same landmarks。

 however， when you observe the landmarks， right？And the landmark itself is part of the variable。

It is a look closure， but it's indirect。The constraint between poses is not directly encoded in the graph。

 It is via the landmark。Right，Because now x1 and x n -1 are correlated。We L2。

If you marginalize L2 from the graph， then these to get connected。Right。

There is a way to marginalize it。You can do that。By doing that。

All the edges that are connected to that landmark get correlated。So我你 the钱。这是我不。

I seeing that at XM you observe the by line。Or place that X1 US also observed， So that。

Maybe landmarks， it doesn't have to be real landmarks。 that's my point， right。

 Maybe this was this is such。Somewhat abstract here。 But maybe it was via landmarks。 Maybe it was。

Maybe you use deep learning to just。Detect， this is the same place。Then you。

So you can use deep learning based place recognition as well。Which is an interesting development。

 and we want to see where it goes and hopefully we can use it。

Although the generalization is a challenge again。The different domains。

Maybe you have a way to detect this is the same place。

 and then you have to establish a geometric relationship such as C2。

This can come from a variety of algorithms， image registration， point cloud registration。

Maybe it's end to end again。Maybe the same deep network can give you a pose as well。

By feeding it to the similar image。So there's no limitation how you do it as long as you have this constraint。

But it is very specific。What type of constrain you get once you define your variables， if it's S E 2。

It is not abstract that this constraint must be also some sort of。SE2 measurements。Between two poses。

 the relative transformation。嗯。talking about closure。Can not just on me。But also， for example， don。

Right， this is coming from oometry。You won。Luop closure does not come from atry。Right。

 if that was your question， the look closure comes from perceptual sensors。

 sensors that can reoberve a reference。A landmark is a reference。

 we can reobserve it ortry by counting its steps。Andve rotations。Or integrating IMU。

Will not give us some reference that is reobservable。Right。What if we have to cents for example？我埋这。

Iically you up and used this kind of an exposure for example light off of 10 hertz on that。

Camera will have a 60 first。So let's still have to can foot as the bro right？

So let's break down your question。 We might have multiple sensors， these sensors。Our heterogeneous。

 we might have lidar camera IU。They operate at different frequencies。And all of them are challenges。

Because you need to decide where， when you place a node and based on what frequency。

 if the sensors are coming and operating at different frequencies。

That might be a problem that we're going to talk about it next。Again， in abstraction。

 there is no limitation。 In practice， that's an excellent research topic。

 How do you solve place recognition problem using heterogeneous set of sensors。Lar camera。

Maybe per at the same time， because you might sense the roughness of the ground using IU。

 although it's not enough。But it might add something based on。

The type of ground you're navigating on。How do you use all of these sensors to solve the press recognition problem better。

Don't have an answer， that's a good research problem。I mean good enough to do a PhDI。Right。

Probably we will see more and more papers on this topic。In the coming years。

 because deep learning now allows us a way to。Process heterogeneous signals。

And combine them into a latent space representation。Otherwise， it's difficult to。Turn IMU signals。

 for example， and point cloud and images into a set of features。That is sufficiently useful for。

Something like this。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_112.png)

All right， so once you know how to build this graph and in general。

 you can have as many senses as you want。There are different variations of。The problem。

 One famous problem is bundle adjustment。Oneal adjustment historically studied in computer vision community。

It is a problem similar to s， but you have a single camera。If you have a single camera。

 typically you don't have autoometry。Although you could get visual damage。

 but bundle adjustment is not formulated like that。

 You try to reconstruct an environment as a set of features。And camera poses at different time steps。

So all you have。You have landmarks？And hopefully， you reoberve these landmarks again and again。

 So you establish edges based with different nodes。And then you have robot。

 the camera opposes at different time list。So there is no auto age。

This is called bundlele adjustment。So you can easily also formulate it in within this factor graph framework。

By the way， nobody's asking， what is this hanging there？You' all know that。Homework 7 is working。

It's the prior， right？So。Made my life easier by getting you start early。Okay， so prior。

 why do we need prior。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_114.png)

It was important enough that it is here。If it wasn't important， we could just not having it， right。

Any of the are。Perfect， yes。 So otherwise， everything is relative to each other。

 If everything is relative constrained， how can we solve the problem with respect to some reference frame。

Although there is no。universalive reference frame to discover。 But wherever we start。

 that can be a reference。 that can be 0。So it's necessary to anchor the graph。By placing your prior。

 this prior can be 0，0，0， you know， for your pose and the very tight covariance is to make sure it's not moving around。

This prior will make the problem well defined When you form the linear systems， now you can solve it。

 otherwise。The map， the whole world， will rotate and translate。 Everything is relative。

So the prior is very important。 Sometimes you see even there is a prior on the first two nodes。

Theoretical is not necessary， but。Sometimes you see the problem is hard to solve。

And you have information than you may as a place more priors。

So prior is important so that we have a reference。Another question。Is everything is relative。

 can I have。What type of factors I can have？All we see here are factors that are connected to two nodes。

I want to have examples of factors that。Are only connected to one node or factors that are。

Connected to three nodes。Is that possible。GPS， so if you have GPS。That will be a unary factor。

Because GPS is telling you your global position at any time。

It is not a relationship between two variables。It's just for that time。

What is the example of non GPS unitary factor？Deth sensor。Well， depths， you need the map。

 You need the landmark for some reference。 But， yes， the depth， if you talk about height。

And you know， that's your reference。Yes， but one of them should be fixed， right。

What if the height is changing？The vehicle is also moving up and down。Gyroscope。五れ的出了。Is it。

Gyroscope is we integrate between two。Orientation。Magnetometer。

It is a correction of your orientation， with respect to reference。Right。I guess yeah。

 suppose we could。 It's a magneto for legged robust forward kinematics， if you are。Just。

Having your contact points， your leg。Point in the variable。

 And then you always get the relative pose。So basically， that will give you the height of your。

Black respect in the body frame。So it is possible that can， depending on the problem。

 you might want to think outside of the box。 It's not just wheel encoder or IM U and。Camera。

 what is a tertiary factor， That's something that。These factors are cut binary because they're connected to two nodes。

What is an example of a factor that is connected to three nodes？

You see less because it gets complicated。You want to have a good reason for that。

An example that we're seeing in our project is like the sonar， for example。

 doesn't create scans as quickly as LiDarR does， so for example。

 one flow rotation might take 20 seconds。So if you're keeping track with pose over time。

 you have scans sorry beams that correspond to the same scan over time。

 so you have to just stitch them together and combine it into a single state or you just keep track of。

Constraints that connect to。That correspond to the same scan that you want to later on these for。对。

A collected at different states's a couple so our data and you need to delay。

Establishing the connections。 So I'm going generalize that when you need a delay to。

 we need to delay constructing that constraint， you might wait until you have more observations。

The consequence of waiting。Is that you need more variables in the graph。To establish that constraint。

 because youre also tracking it over time。 what variables are seeing more。So if you delay that。

 if the definition of the factor requires some delay， then you might end up having more notess。

 A simple example is when you need to triangulate a feature。

Maybe using a streic camera or monocoic camera。To have good initialization of the features by observing it from multiple views。

You cant do that， and that tends to make estimation better。The sonar example is good， I think。

 in underwater。That is done。So it's， it's possible， right， It doesn't have to be binary。

Your the sky is the limit。 You can model。In any creative way you want。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_116.png)

So we like this generality of the framework。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_118.png)

And it's flexibility。So this is a very cool problem。 They have a lot of fun examples and。😊。

Reconstruction and visual Islam。You can search。To learn about his history and how people solve it these days。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_120.png)

But typically， it's a graph optimization solver。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_122.png)

Okay， so now you learned how to。Model the problem of sensor fusion for a state estimation as a factor graph。

The question is how to solve it。Now， you are familiar at this point with GTS。Or another library。

That you might have used your project， G2。For constructing this graph and。Solving it。

 So it is nice to have these libraries。😊，Your concern is building the graph and modeling it。

 not implementing the solver， however， it's good to understand。

How these libraries approach the problem for solving it so efficiently。So what's。The barrier here。

Look at this slide。 Tell me。How do we get from there to？Lease the scores。The winner。

Get to leave the class。Yeah。😊，Early dismissal。You don't need to be here。Alright。

 so to keep it fun and。Interesting， we're going to talk about this next time。

 So next time I want to write down。How I can write this factor graph。

And get the overall objective function。 And under what assumptions。

 it ends up being at least the squares。 So want to write down that and walk you through it。

 because if I tell you， it's not as good as writing it down。This time。

 you have to accept that under certain assumptions。

 this graphical formulation will boil down to a nonlinear least squares problem。

In the same sense that you've seen before when we model the RGBD camera。Yeah。pon。ベシ。

For this approach。They was approach it。The question is。

 what's the motivation for this graphical modeling as opposed to。

Partiggate filtering or calmman filtering。The filtering， which is part of today's lecture in the end。

 to summarize is。The problem of estimating。You're a estate at only the current time。

Whether it's the particle filter or columnmen filter。

This smoothing framework is the problem of using all the data you have。

To estimate the entire history， trajectory。At discrete time is steps that we track。In filtering。

You are relying on the current gas to linearize， for example， extended columnman filter。

What if the linearization is not accurate。So we go ahead and we correct。

 we incorporate information as much as we can。And this process will continue。

There is no chance or opportunity to go back in time and correct past mistakes， linearizations。

Likewise， in part of a filtering， that's not possible。A low particle filter is multimodal in。

More powerful in some sense。In this framework， we are constantly。Optimizing the entire trajectory。

Based on information we receive at future times。Because I'm solving a linear Lisa square problem。

 and I'm looking at the entire trajectory， as in my entire estate， right。

 So this is the fundamental difference。Does this part make sense。So。On the surface。

 you see that okay， it allows us to correct past mistakes， right？Now， it's very。

Easy to think that world carbon filter is probably faster because I'm just estimating one。State。

And this is a slam， right， We're talking about estimating landmarks and robot posts。

 You need to track the map。So you need to track the landmarks。

Or at least a subset of landmarks in your state， but only track your latest posts。Okay。

 that will be Eke for Sla。Or part of your filter Islam。In this case。

 we are tracking the entire trajectory。And。Also， the map， the landmarks。

It turns out it is slower to do what column filter is doing， why。Because when。You get rid of history。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_124.png)

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_125.png)

I excluded that slide I thought you're not going to ask。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_127.png)

So I'm going to drive。So it turns out when we marginalize。History， it makes the problem dense。

 We lose the sparsity， whereas when we keep the history， it keeps the problem to be sparse。Because。

The number of landmarks can be large， regardless of number of poses。We end up with solving events。

Problem， so you have these landmarks， you have these pose， right。And you have。These landmarks， right？

When we solved the least squares problem， and we formed the Jacobuban。

 this Jacobubian is a sparse matrix。When you marginalize it in filtering。What we get is。

So to marginalize， I'm going to。Make them black。So this last one is active， right， in filtering。

 we're marginalizing the history。Everything with everything gets correlated as as a consequence of。

Now， this is proven， right， can。Do the marginalization。Which is not very difficult to do。

You have to do it in the information form， in the inverse covariance form。

When you marginalize the history。I are the fact that we。Removed。

It causes the problem to become dense。 This graph in some becomes fully connected because everything is now correlated through the latest robot pose。

 That's the only thing we're tracking that should be correlated with everything else。Otherwise。

 it doesn't mean anything if they're in the state， right。Now， it turns out that this is a bad idea。

 because。If the problem is dense and you're crack thousands of landmarks。

It is extremely expensive to solve this problem。It's computationally。

Cubic to solve a linear system that is dense。And so large。However， the sparssity allows us to。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_129.png)

As you can see here。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_131.png)

When we formulate the least the squares problem。The Jacobubbian you see here。

 the blue dots are the only points that variables are connected through the model。When I said dance。

 I mean。Everything is nonze here， right。You will never get a real time s system。scalability issue。

This was the knowledge。Discovered around 2004，5，6。2004 and5。So since then。Basically。

 everybody gradually switched to graph Islamlam。 So this is sparsity and maintaining a sparsity requires to maintain。

 to maintain the history。 That's why that's the main difference。 So it is。Faster。And。

Better because we can correct past mistakes。Somewhat counterin。先开有咩。you described that specifically。

If you're using filtering， but it seems like there。

Slam methods that use filtering that won't suffer from that problem because we're just throwing away past data or。

You're like not looking at all of the like。So like for example。In Ro 550。

 we do real time s particle filter。And。That case starts pretty easy to implement and it doesn't have the problem of life。

Taking the kinds of the three amount of time because we're only observing light。

The think are you're only for carrying or pose against the things that you need。

Not all that the evidence。Yeah， so the comment is that。

There are slam methods that perform the marginalization， however。

They work with a subset of landmarks or maps， and they perform well。And the example you're giving is。

Fastster slam， particle filter basis slam in occupancy grid mapping。Now。

 that tends to work well because。It is in 2D and in a flat ground。

 Nobody dares to run that on a quador or in 3D slam， visual slam， right。

 We yet to see somebodys doing 3D。An aggressive visual Islam or other sensorenss， using that method。

So it's a very contained and limited algorithm to that educational setup in the lab that you were talking about。

 right。It's good for indoor。Experiments， and。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_133.png)

Some indoor environments may you dealing with flat grounds， I think it's a good algorithm。

But it doesn't solve the general problem that we're interested in。Right。Besides。

 it's not really allowing us to efficiently incorporate more sensors to make it better。

It is a very specific method of using a particle filter and an occupancy grid map。However。

 I want to connect that to the idea of dancelam because。We're talking about landmarks。

 The map can be a dense reconstruction of the environment。

 that 2D occupancy map is an example of that。The dance s is also an ongoing research。

 It's an interesting problem。 So how can I localize and also reconstruct the environment。Dance or in。

 and it's sufficiently。Complicated way that I can see the scene。That I'm observing。

 using my lesss say cameras。That is a more challenging problem。Although again。

 the solvers are using graphical。Construction for that problem as well。Here， we are talking about。

Landmarks as a standard example of it。So another natural question that you might ask is what's the relationship within？

These matrices in。The graph， the sparsity of this graph。

The parrssity of the least squares problem in the graphical model。

 it turns out there is a one to one correspondences。What we see in the linear algebra。

Although it's linearized， you can formulate the linear problem to see the correspondences that the graph structure is exactly describing the fill in that you see in this Jacobkuan matrix。

Because it shows the connectivity of your variables。In the sense of linear algebra， using matrices。

So that was another discovery that they are all related， whether you use。Linear algebra。

 graphical models。They， they are。Showing the same thing in different languages。So that's encouraging。

在 weR。Next time we' will see how to get the linear least squares problem if it's not nonlinear。

 we're going to linearize it， of course， solve it using Gauss Neone or Lenberg markrot or any other methods that we discussed。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_135.png)

And of course， you know that you can form the normal equations。If your Jacobban matrix is a sparse。

There's a lot of zeros。When you form a trans a， it's also a sparse。

This is your information matrix inverse of the covariance matrix。So we have to do。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_137.png)

As far as QR。Or。The fars。Tlesky factorization for solving this problem using。

Forwardward and back executionstitution。So， we will not use。

QR factorization that's for dance matches because then you pay the cost of the。Full factorization。

And one。This is supported in many languages， but one particular。

Library that handles this is Swish part。Sweish parts provides a range of。

Sely algebra methods for larger scale problems， including。Sparrs Phillesky and rank one update for。

Your factorization。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_139.png)

So if you have。This idea of。Food bundleal， just and Islam， is still the graph will grow， right？This。

It's nice to have。 And it has advantages over filtering， but it's still。😊，As time passes。

 you will add nodes and this will quickly becomes intractable。Because you have so many variables。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_141.png)

Even though it's a sparse。That's not sufficient。 So one idea to solve this problem is the idea of keyframes。

What if you drop some of the frames， Still， you keep the history to maintain this sparse structure。

We dropped some frames。And only use。Key frames， frames that seem to be importanted。

So once you deal with keyframe， the problem becomes more manageable computationally。

How to detect detect key frame depends how you。Used to establish factors。 Maybe it's using camera。

 Maybe you take overlap。Maybe if the overlap between some previous keyframe is falling。

 less than 30% or 40%， you initiate a new keyframe。If you're moving faster than certain。Speed。

 maybe you trigger new keyframe。 Maybe there's a time limit on how far it's been since the previous keyframe。

 That's another condition you start a new keyframe。

 So a range of conditions probably usually is used。Together to decide when to add a new keyframe。

So having too much data is a problem， actually， so keyframe idea will make it tractable。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_143.png)

Another problem is。Well， we can construct a graph and we can solve the least squares in batch。

This makes it offline。 If I have to solve the problem every time from a scratch。That's not。

Very efficient。So the natural question is， can I solve it incrementally by reusing past information？



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_145.png)

Now， the answer is， yes， you can。

![](img/2179d03ef9e8cac9a781533e6bf0d0bc_147.png)

And that's the algorithm called incremental smoothing and mapping Iam。

Which is the Iam solver in GT Sam。In the linear case， it's exact。

 If you're dealing with linear systems and。You don't have to re linear your eyes。

When you factorize your matrix， this。R using your let's say QR factorization。

When you add new rows to your Jacoban， right， obviously。We're going to have part part of this matrix。

 that is。Not going to be upper triangular。There is a way to。Update。

This factorization wander at a time to zero out everything below the diagonal。

And that's the problem of incremental factorization。

Sometimes it's called rank one update of your factorization。But again。

 we want to make sure we are maintaining the sparsity of the matrices。That's the condition。

 so it's possible to do it if it's linear you can do it exactly and you can update this in constant time。

It meansan every time you do this， you just need a fixed budget。

 It's not going to grow as you add more date， more rows。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_149.png)

So that's good news。 And a particular algorithm that is used is called。😊，Give end rotations。

There are several algorithms for QR factorization， givens rotation forms Q matrix。

 your autotagonal matrix is a sequence of rotation matrices。So。At any time。

 you just need to apply a new rotation to。Correct， the previous。Factorization to。0 out。

The must bottom row， right， So I'll give you an example of this code of it done so you can see it if you're interested。

So that's good news and it's constant time， that will make it。Incremental and online。Now。

 somewhat bad news is that， well， in practice， the problem isn' that linear。

 We can assuming the previous linearizations are good enough。 We can keep doing this。 At some point。

 we might want to。Re linearize。 So at some point， you need to pay the cost of doing some batch。

Correction。But this still is's very powerful and enables incremental solution to Islam。For example。

 if you。Havelf 21000 variables。You cannot possibly handle 21，000 variables in a columna filter。

This is the idea of manipulating them。And a common filter is terrifying。

Whereas this modular framework is。Way more friendlier than。

A filtering framework for constructing this problem。 So if you have 21000 variables。F， the matrix。

Was dance。You had to store 1。7 GB。Filtering would make it dense。If it's a sparse。

 you only store 1 MB。So the gain is huge。And this was a milestone in Islam using a srsity to solve the problem。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_151.png)

So that's it for today。 Next time， this was for giving you an overview of the factor graph。

 And what's the story Next time we want to write down。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_153.png)

The factor graph。Show that how it reduces to least the square problem。

 where does the sparsity come from。And more discussion on actual calculations。

These are good references to read。And a standard of the lecture。



![](img/2179d03ef9e8cac9a781533e6bf0d0bc_155.png)