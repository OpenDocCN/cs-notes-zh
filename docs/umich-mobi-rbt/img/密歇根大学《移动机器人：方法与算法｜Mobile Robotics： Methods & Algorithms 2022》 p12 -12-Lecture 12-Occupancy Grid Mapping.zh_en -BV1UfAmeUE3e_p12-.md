# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p12 -12-Lecture 12-Occupancy Grid Mapping.zh_en -BV1UfAmeUE3e_p12-

![](img/e29a3be8da83cd7d5c7325fd2d883b00_0.png)

Welcome to the first lecture on robotic mappinging。In the next two lecture， we will talk about。

Building a map of representation of the robots surrounding based on relative noisy observations that we obtain using onboard sensors。

So the first idea， which is the most common way of building maps。And many robots and 2D environment。

 or。3D environments when the robot is。Moving on uneven floor。That we can assume the map。

 the layout is 2D， and that's enough for the robot to move from one point to another。

 it's called occupancy grid mapping。And it is a good way to。

Introduce you to this area of the mapping。 Next time we will talk about 3D， the extension of it。

 some of the ideas that will。Basically fix some of the problems that we raise for this basic method today。

We will also show you that there are open source libraries that you can use at this point。

That can address a lot of projects that you might work on。Without building on it。

 But the research is ongoing。 and this is an open area of research in robotics。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_2.png)

The first thing we need to talk about is。The idea of the map。How do you define a map。

 How do you represent a map， How do you visualize a map？There is no unique way to do that。是的。

That is a fundamental problem， because if there is no unique way to do that， then。

We can come up with several ideas， many ideas， and depending on the application。

Some of those ideas might be shown to be better or more efficient。

 but depending on the computational resources we have， we might opt for a particular representation。

So， that leads to。Multipplicity of ideas for mapping and how to show the map。For example。

 in this figure。On the right。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_4.png)

You see a data set called Victoria Park data， this is a famous data。

Was collected in late 90s or early 2000 in Sydney。And that's where I used to go to school。

 That's where I did my PhD。I used to swim in this pool。And there's a shopping center here。

 I used to do my groceries there。So this is a very important data set to a lot of people。

But the landmarks you see are。These points。 Now， what are these points。This is open source。

 There was a truck。Like a utility vehicle， they moved around the park and collected the data using range finders sensor sos。

And autoometry for。Real movement of the car。 So the landmarks， the points that you see。These are。

Obtained after processing。Raw sensor data from a laser range finder， a 2D point cloud。

To detect the trunks of the trees in the park。So， the entire tree。

When you detect the cross section of it。Which is the height of the vehicle， not very high。

Itll probably give you some。Line， if he。If you look at it from the front view。

 but you can consider that as a point。 So there is a part that processes that data and will give you these 2D landmarks。

It is open source， it's a piece of Mala code， that will process it for you。

And that's one way to represent a map， because now we know that。If we。Fix the coordinate somewhere。

And then if we knew the。Location of every landmark。Let's say。X， L and Y， L。

If we move and we can detect these landmarks。We can localize using some of the ideas we learned。

 maybe an extended column filter， maybe a particle filter。We can solve the problem。

 And this is one way to represent the environment。Now， the challenge is， of course。

 that in this case， we don't know the locations of these landmarks。 So the research is on Islam。

 simultaneous localization and mapping。 Not only we want to recover the trajectory localized。

 but also we want to estimate the location of these landmarks。

Because we only know them relative to the sensor frame at this time step as the vehicle navigated the environment。

So this is an Islam problem。 But if you know the landmarks， this is one way to represent a map。

And we can use it for localization。Now，Another idea that today we work with it is。

Representing the environment in a way that you could call it dense。

 That means for every part of the environment， I am modeling some。Here， a probability。

The probability， if that particular grid or point is occupied or not。That's another way。

 Maybe it's 3D。Maybe we want to reconstruct and show。The objects， the way they are。 That's also。

A representation。But you can imagine that this 3D is， of course。

Much more intensive computationally than something like a 2D map。

So volumetric map versus feature maps are one way。Where we can talk about mesh。

 a lot of research in computer graphics is about how to model objects and show them。

Some of them are really good。 Some of them are not directly transferable because they are， again。

 intensive。In terms of computation for。Onboard computation。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_6.png)

So that's one problem。 And today， we， we're going to talk about。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_8.png)

This type of mapping。 And I'll tell you why。We might need a map like this， for navigation。

As opposed to landmarks。That does not mean that we cannot use both of them at the same time。

 but there are benefits in the dense reconstruction that we are not getting from just tracking points。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_10.png)

So the great maps idea is that it discretize the world into cells。

So this great structure will be rigid。That means it's a piece of。Map grid in your memory。

And it's rigid。 It's not going to change。What we're doing， we're just updating the belief。

 their posterior。The probability of occupancy based on observation we receive。 And we。

 we want to update it reccursively， of course， because we see。A chunk of the environment。

 And then we move。 We see another piece。 We want to reccursively update， update the map。Now。

 the fundamental assumption that we will go over it is that these。Gres are。

Independent is statistically independent from their neighbors。

 And that is a fundamental assumption to this type of mapping。So each grid is assumed to be。

Either occupied or free。So we only talk about the occupants。 If it's occupiedcc。

 that means if you hit it， this iss an obstacle。And。

You might not want to do that if the goal is to do obstacle avoidance and navigation。If it's free。

What does it tell us？

![](img/e29a3be8da83cd7d5c7325fd2d883b00_12.png)

We'll get to this soon。Here is an example of an occupancy greet map。This is a building in。

Fibber campus in Germany。Again， the data set is open source and is's available。You see。

 when you build the map。The black。Clls， the color map is usually gray scale from 0 to 1。

So the darker cells means occupied。And brighter means free。

 when it's gray is in between range that we don't know it's unknown。

Now you can flip the color map or you can choose different color maps， but this is。

Very standard in papers and literature。So as you can see， when you zoom in。Once you build a map。

 because the grid structure is rigid and resolution is fixed。

 there's no way you can increase this resolution。You are bound to this particular grid size。

You use your data。 The map inference is done， and you cannot increase。Or enhance that resolution。

So this is built in， it's baked into the algorithm。Can be a problem， or maybe not。

You're going to still。Accomplish a lot of autonomy tasks， using this map。

But it is insufficient for general。3D scene understanding and tasks for today's applications that we have in mind。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_14.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_15.png)

Now， the notion of free space is important if you want to plan。

If you have set up landmarks in the environment。And if you want to move autonomously in the environment。

How does a robot know if a particular space is available for navigation or not。

 just because we don't observe that area doesn't mean it's safe to navigate。That is somewhat obvious。

So it is important to know where we can go。Where we hit an obstacle and when we don't。

 where we don't know yet。So the accluded area or the areas we have not explored yet。Are unknown。

They can be free or they can be occupied。But the robot knows that if you want to go from point A to B。

Maybe。You plan a path like this。So the planner， you can use something like A S star or。R，RT star。

It will find a path that the robot can navigate over。All available cells， free cells for navigation。

 given previous data。So that's test the importance of free space。Now。

 what if somebody is moving in the math？Or at the time that we mapped the environment。

 maybe it was empty。 Maybe now it's not when the robot is navigating。That's very important。

 The environment can be dynamic and not necessarily static。For example， maybe this is a museum。

 We have an example of a museum later。Maybe you map the building when it's empty so that you save the map。

 the robot can navigate at a future time。But when we visit。

 maybe there are a group of people visiting the museum。And it's not as easy as moving A to B freely。

So this map， as is， is not capable of modeling dynamic environment。

 So there is also an assumption that we will see。That the environment is aesthetic。

 so the world is aesthetic。And then we infer this map。 This is a。Built in assumption to this method。

If you only use ometry。To build a map， you might end up with something like。This figure。So。

 if we are not solving。Slam， that means we're not simultaneously solving the localization problem。

But we're going to assume we have access to robot poses from somewherember。And the problem is。

 in reality， of course， you don't know the ground truth。Ultimately。

 you want to get it from a source that might solve the problem for you from some measurements。

If you get it from oometry， because the oometry。Comes with drift。

 You might be end up with a map that is inconsistent。

 So the inconsistency in map refers to when maybe you have walls。From multiple scans。That are now。

Not being aligned well as a result， what you see。In the reconstruction does not match。What we see。

 the reality， the structure that we see around us。And that is a problem。

If you have a good Islam algorithm， maybe it solves a localization problem for you。

If the localization is accurate。Then you can build a map that looks clean like this part。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_17.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_18.png)

So besides being the environment being dynamic， there there are also other motivations for building maps。

So a lot of times， even though we have prior information about。The layout of a building。

 if it's an indoor mapping problem。It's probably good to know the structure， but。

The setup of an environment can change over time。 For example。

 the CAd model might have this layout of furniture。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_20.png)

You can see here。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_22.png)

But at a later time， the setup can change。What if environment itself itself， we can。

Have small changes。So the ability that we can send a robot and reconstruct the scene as is。

And do it fast as frequent as we won。It's very useful。

Because then we don't have to manually maintain and update the maps to feed it to maybe a robot to navigate。

So just like localization， this is a very fundamental problem in autonomous robots。

Something that is more real war， for example， a self drivingriv car。

There there are high definition maps。 The car can use it to localize and move， as they do。However。

 maybe。Because of some accidents。Or road work。The road network that we assume we know is not the same。

What about that？Now， suddenly， maybe。We have to navigate on the opposite size， because。

That's just how it is。 There's an accident。 Maybe the cars are turning， taking turns to。

Move along from east side。 And these are not things that we can hardcoat into the robot that will happen at a particular time。

 These are unexpected events。That requires requires online scene understanding and mapping。 Now。

 that is a bit much harder problem because we also need to understand some signals。

 Maybe police officer is telling the cars to come now。 and then the other side。

 the autonomous vehicles will not understand that。So that's a much harder situation。

And this is maybe a more。Mageable version of that。 We want to just model the occupancy。

 not that we understand the intention of people around and reading different signals that we've see in the environment。

Because the light can be red， but the officer is telling you to go。

And you need to get a resolution for that。 It's easy for us。

And it turns out it is extremely difficult for a computer vision algorithm to understand that。

So there are many motivations to have this capability for the robot。

 to build online maps and understand the scene。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_24.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_25.png)

So we navigate in the environment， and we collect some scans using。A range finder sensor。

A range finder sensor will shoot infrar red beams。With some resolution of the beams on the sensor。

 if it's 2D。It's like this。And some maximum range， and it will return。The distance to an obstacle。

To the sensor， it measures the time of flight of the infrared light。

We know the speed of the light and then we know the distance。Now， when people moving around。

 you see all these outliers and dots that。It's true that they were obstacles。

 but they're not a static part of the environment。 We don't want that in the map because they will leave artifacts in the map。

What we want to do is that。To come up with a probabilistic method that ideally can give us this clean map。

So we want certain level of robustness to outliers and moving objects， if it's mild。

So we can still reconstruct these statics， hence， this probabilistic idea of inferring a map makes sense because we deal with some level of uncertainty。

In what we observe， observations are not。Absolute and deterministic。我说是是。不是谁。对。So the question is。

 can we do post processing？To remove the outliers， yes， but we want to build the map as we see。

If you have the option to process data offline。We can build something like H maps。

 high definition maps for the cars， so we can do a lot。But if we want to build the map under fly。

 as we operate。You have a very limited time window to process that data。But， yes。

 maybe you build a map and then you look back at the history with some software engineering。

 Maybe you have a parallel thread to。Look through some other parts of the map and update them based on some other ideas。

 So it's， it's possible too。嗯。Come up with clever ideas。Today。

 we're going to talk about a very basic introduction， how to build this map online。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_27.png)

So the map occupancy great mapping idea was。Introduced in mid 80s by Mora Vaan Alphas。

Oh I was just great， talking out。Is it。嗯。Is it reliable？InDifferent environment right。Right thanks。

Or。Or is it like？Yeah，可始。The question is， what happens if it rains？Yeah， we're like now our desk。

Nothing happens if we're inside。So that's。That's what we know。If you're outside， well。

 that's a problem。Just like cars moving around， people moving around。

 That's a problem we have to deal with，So we're not zooming in too much in these particular challenges。

 but all of these make the problem only harder。You fix one or two of them。 That's already hard。

 And there are ，10 or 20 of them left to deal with。And that's again。

 what makes this area so wide open with so many ideas， so many people working on。Robotics mapping。

Now， one question that is relevant to today's research is that some people actually say that。

 why do you need the map。Why not？Just go for a map list navigation， you can do end to end。Mapping。

So there is a famous paper by Professor Kifers here in Michigan。 It's called the Ma in the head。

How do we。Start the map。Are we seeing the map or we seeing images？

If you refer to yourself what your eyes are seeing。It looks a lot like images。I do not know。

With certainty， but。It's more relatable as if it's a camera that。Is seeing the scene。

What is the representation that we have。Whatever it is， it's pretty good。 We can。

Accomplish a lot of tasks。So， it's。It's a compelling idea。

 maybe there is no need for explicit representation。

 and maybe there is an abstract of space that can capture everything。Now， the problem with that is。

There a black black box mapping for a robot。Might be doable， but it will not make。The method。

 explainable or interpretable if a robot wants to interact with humans。

Imagine a team of rescuers are going into the fire somewhere in the forest too。

Help people imagine a team of a team of robots also collaborating。

 How are they supposed to exchange information and collaborate。If。There is nothing to share。

 They can just talk about the end results。So it might be beneficial for the human team to have access to the areas that are explored by the robot。

By knowing and seeing。In some way， what happened and what was mapped。It our value is to it。So again。

 just like a lot of ideas， it's not that one is correct and the other one is wrong。

 There are certain applications that you might want。To have an interpretable map。

Probably there are applications that maybe you don't care， maybe。

If you try and maybe if you accomplish the mapless navigation， that will work。So， back to。

This invention in mid 90s， they used noisy saar information， acoustic signals at the time。

But was not a laser range finder or if there was probably。

It wasn't something that they had access to in robotics lab。

Because we see laser that a lot of people think that's a。Mass destruction weapon。

 but it's like a remote control。Laser。That's why sometimes there are export limitations and constraints on these sensors。

Becauseuse the thing is's laser。You're going to cut people with a robot。

It's more like a remote control。So they had noisy sonar。 So acoustic signals， obviously。

 the acoustic travels in a cone and。It's very rough。 It's not sharp， like laser to return。A point。

It's a rough measurement of an area that maybe retain a point。

 but it corresponds to that area being occupied or not。So they called it mapping with knownun。Poses。

So， you know， the robot pose and they tried to build a map。 The question was how to do it。

 And their idea was to。Let's do this probabilistic reasoning to incrementally update the map。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_29.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_30.png)

So in 1987， we had occupancy Greek maps。And I think that we were working with the Stere cameras in NASA JPL。

Also， there was a time that I were also talking about visualtry。Occupancy mapping。

So I was not with them， I was born in 1987。But you can read some history。

So it wasn't solved because part of my PhD was on occupancy grid mapping。

Even though I was born in 1987， so I used Gaussian processes to build the same map。

That's a regression way of doing it。 It's not discreteet anymore。 Now it continues。You can get。

Variarianance。You get a whole distribution over the environment。

 It captures the correlation that you have with。Different points in the environment。

If this is a table and there is a point here that you observe and is's occupied。

 there is a really good chance the nearby points are also occupied。

So that structural correlation can help you to have better inference， more accurate inference。

 even though。The point cloud observations from the sensor are still a sparse and noisy。

So a better model can give you better results。 But the cost of that Gaussian processes was that。

The method was that。It is cubic。To run the inference， you can come up with。Some simplification。

 But in its native form， you have to pay the cubic computational complexity because you have to invert a matrix that is large。

For the training data。So next time we will make this continuous。

 but some with a new method that it is from the family of kernel methods， just like。😊。

Galauussian processes， but it's an approximation to Gaussian processes。It uses the inference time to。

Log n instead of QbB。So that's what we're going to talk about next time to make the map continues and 3D and semantic。

So no room for。If you want to do a work， finish it， don't leave a room。I'm not serious。

 There's still a lot to do， because you。You add all these good features and you say， well。

 this is it。 This is the end。When you run it， you see， there is still a lot of problems。So it still。

 even though it continues， you need to somehow represent it in a way。Right。A played with the。

Gre back a little bit。 You model the ground， and the vox are。

 Vox cells are 3 degrees are still up and down。 you see， it's like minecraft。It's not flat。 And。

 I mean， we know it's navigable。 and then the robot moves there。 But if somebody gives。

 gives that to you and。It looks like off road， even though it's a road。So still a lot to do。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_32.png)

But it's progress。 Now， imagine you have an area that is 25 by 25 m。

You need to pick a resolution for the grid。What resolution you would pick？Clearly here。

 we picked 25 cm， but。It depends。Is1 m。Greatre size， good for navigating inside a building。

 Probably that's a bit too coarse。If you pick one centimeter， then maybe that's too fine。

 And you need a lot of memory and calculation。 So there's a tradeoff based on your application。

 If you use this method。You probably want to tune a resolution that。

Makes solving the problem feasible while you can use it。

So if you have 25 by 25 m area and the resolution is 25 cm。Then you're gonna have100 by0 grade。

And I will give you。10000 cells。 That's already a lot of variables in a localization that you do for the common filter。

In 2D， you have three state variables。X， Y and heading。 right now。

 this is also a state submission problem。 We want to infer the map， instead of the post。Now。

 currently， the state is 100，000。Or 10，000 here。And it's not that big。 This is 25 by 25。

 This is a relatively small area。So， clearly。And naive。

Attempt to run and off the shelf inference might not work， because。

Then you have to handle a lot of data。 You can't just run it。Method like Gaussian processes that。

Handles everything in batch， tries to infer something for you。So that's what makes this idea good。

 We can handle sizes like this，Let's say we consider the state not to be a continuous value。

 to be a binary value。1， if it's occupied，0， if it's free。

How many possible maps we have for this probabilistic estate。So we have 10000 cells。H cell has。

Two possible estate。So you get。two。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_34.png)

To the power of。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_36.png)

10，000， something like this。But it says something else here。This was an old joke， I had to unlock it。

This is not my slide。Now， this is binary。This10 here is。To in binary。If you， if you valid this。

 it will tell you roughly too to the power of or。I'll give you something like this。

 but I think this is binary。有。So you the of X Y I。Thank。都看。The question is。

 do we consider the map to be the configuration space？Just like we did for localization。No。

 not in that sense， but it still is part of the state that we want to estimate。

And if it's a dense reconstruction。Now， regardless of the specific value here。

 there's a lot of variables。This is just small examples。Show that it grows exponentially。

 You go to 3D。 this grows even so much faster。So， we don't。

For a state to build a traditional estateestimator like a common filter or particle filter。

 Although you can do such a thing for each grid if you want to individually。But never jointly。3份支。

It is。 It is ultimately like a landmark is a position。 That's right。

So there are ideas to run tiny E KFs or。Part of get filter to estimate some quantities for each cell。

 people do that。What is。And you can consider a neighborhood if you want， But it's rare。

 its it's never for the entire map， because that's just not tractable。So what is the idea for。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_38.png)

In France， that's what we want to learn today。So the assumption one。

 this could always list your assumptions when you're developing an algorithm。

It makes it easy for other people to attack it。Maybe not something that you like to hear。

But that's how we can make progress。 Other people can come and maybe relax the assumption， or。

Change it to a milder assumption。Becauseuse if you make enough strong assumptions。

 usually you can solve anything。And then the goal is if we can relax the assumptions and make the problem more realistic。

 Eventually， we will have something that。😊，Has utility in。Real life。

So the first assumption is that a cell is either occupied or free， that this state is， in some。

 binary。So that leads to the representation of the environment。That that is telling us if a cell is。

Point cell I。The probability of。Cll M I being one implies that is it is occupied and the probability of this cell to be。

The probability being 0 implies that it's free。That's how we model it。

 You could choose the other way around， but。This is how he muled。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_40.png)

So one is the probability of being occupied， zero being free。No knowledge。Something in between 0。5。

 That's the prior。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_42.png)

Now， the world is aesthetic。 We do not assume that we are dealing with dynamic objects。

 although when we operate and build a map， it can happen， and we might come up with some。

Better maybe models to handle them。And some part of the algorithm that we actually implement。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_44.png)

So if it's aesthetic means that if it's inferre to be occupied， it's always going to be occupied。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_46.png)

It won't change the status， it's not changing over time。

We will see that in the graphical model that will come up。In a bit。Now。

 a fundamental assumption is that。The cells are independent。Meaning。

 when we perform inference for a cell。We only look at that cell。 We don't look at the neighborhood。

 And the immediate thought is that。It sounds like a good idea to look at the neighborhood。Yes。

 but that will make your inference more complicated。Which is the next generation of this algorithm。

 but today。We learned that。Co core idea。 That is independent grid assumption。

Which makes it super fast。you can implement it and run it on a very weak computer。

 You can run this mapping algorithm。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_48.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_49.png)

So as a consequence of assuming that each cell is independent。 mathematically。

 your posterior over map。So， the map。Is。Maybe a list or cheaper love。

Whatever number of grades we have or cells we have is a list of all of them altogether。

 That's the map， not just one cell。And the consequence of the cell being independent。

 That means the probability for the entire map is just a product of individual probabilities。

 They are statistically independent。That's the assumption。Okay。No my question is so。

And so my question is。😊，So you can see you're kind of saying that。😊，Yeah， Mar。Thats algorithms。

 great pizza assumptions。😊，So my question is。😊，Do each of these assumptions have？あはい。Weais。

 getting like。我听。对。Great this great。we'll get you the best trade to。Between。Computational complexity。

I you seeing improvements， et cetera。The question is that， do we know particular weight。

That the outcome will get influenced by if you relax or break these assumptions。

We don't have an exact table that says。If you break this， you will get 10% off。

And the accuracy we don't have that but。If you mean that how that will affect the computational complexity and performance。

 that's the case by case， depending on how you do it。Because even though you might。

Subscribe to the same assumption， maybe you choose a different approach for modeling。

And that can lead to better performance sometimes。So that leads to research work that case by case people have to study。

And it is always good if you have an algorithm to talk about its computational complexity。

You can tell people it's polynomial time， but。Is it。To the power of aid or is quad writinging。

Craick is already。Not very scalable。If you're running a common filter， extend a common filter tolam。

 and now you have a million landmarks。That's not going to be scalable。If you have 100，000。

I think it's doable。P有单。So another question is。So to end that question。

 it's the research problem case by case。 Next time we will talk about。

 I'll point out the complexity of this algorithm， maybe we see the method。

So another question is what is the distribution of the map we don't know？

The true distribution is something we don't know。The way we model it， we break down。

This posterior that we don't know what distribution it has。

 It's complicated because it needs to model。This room， for example。

It's not going to be a nice Gaussian。At the very least。

 you can assume this is a mixture of a lot of Gaussian terms。

 If everything was smooth and boundaries weren't sharp。It would be like that。 So we don't know。

 We break it down to the product of many independent。And simpler。Probability distributions。Now。

 we know these individual terms。And the way we model it， we model it as a binary。Distribution。Now。

 the question is good because if you give it an explicit distribution。

 maybe we've worked with that particular formula to have a duration。

 And that's what we're going to do next time。Because although this is binary。

 we're gonna take a direct approach and work with just probabilities。

So that's like directly multiplying probabilities， just like what you did in Markov localization。

So that direct calculation has a drawback that it's hard to infer the whole distribution。

Because if I infer the parameters of a distribution。

 maybe I can talk about mean variances and higher order moments。

So next time we will look into beta distribution， which。But no only distribution or。

Categoorical distribution。Distributions that are explicitly。 They have a model。

 and we can work with them。So for now。Think about this as just the probability between 0 and1。

 We're not going to dive into a particular model。Does that answer your question？So very complicated。

 We don't know this。The goal is to have an approximation of this distribution。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_51.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_52.png)

Which is a visualization of that answer here。If the map contains four cells and they are supposed to be jointly somehow distributed。

 we break it into four individual cells。And we just talked about probability of each cell。 now。

 the joint。Assuming they are statistically independent from the law of probability that tells us the joint is the product of the marginals。

That's why the right hand side。It's going to be P1 multiplied by P2， multiplied by P3。

 multiplied by P4。And you already immediately， you probably want to say that， well。

 you're gonna be in in trouble if you keep multiplying these probabilities。

If one of them is almost 0。We're out of numerical resolution to track that number。 So we don't。

 we don't。We want to come up with an idea to avoid。

Keep multiplying these probabil that can be very small。

Because that will make it impossible to implement numerically。

 So that's part of the discussion today。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_54.png)

Do you want to take a break？Not tired。 I want to dive into theris of a binary base filter。

I told you you said no。All right。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_56.png)

Now， make it more， let's make it more realistic。 Well。

 the problem is that we want to infer a distribution of the map M， given。

Measurements and robot poses。On top of that， we assume that we're going just。

Break down the posterior into the product of the marginal。

 So we want to talk about how can we infer the probability of one individual cell。 If I know。

 let's say a scan， A2D。Range measurement。And I know where the robot is。

 So I want to infer that probability in a global map that I'm tracking。

And I want to update it reccursively if I'm observing that again， next time。

So that leads to a filter。That it's called binary base filter。

 because it's still it's in in that framework of base filter。 But because the map， the state now is。

Binary in common filter， it was a Gaussian distribution。 In part of a filter。

 it was a set of weights like a histogram， an empirical distribution。 Here is binary。It is simpler。

 That's called。Static binary base filter。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_58.png)

So the graphical model is like this， The robot is at time。T -1 here。Then we move to another pose。

 and then we move to another pose。At at any time， because we are at this particular location， X T。

We are going to observe measurement， Z T。And the measurement is caused by the robot being there。

And the fact that the map has。A particular。Shape。So the arrows are showing that what is causing what。

So the measurement is caused by the robot being there and the fact that the reality。

 the map has a particular shape。Which gives us that particular。Laser scan。Rang measurements。Now they。

Typically， standard to color the nodes。 the gray means we know， we know them。

We're not going to try to find values of x and Z。 We know them。M， the white note here is the unknown。

 We want to figure out。What's the value。Now， the reason the map is not moving to different states。

Because it's the static。If it was dynamic， then it needs to evolve over time。

 So you can see that it will be much more complicated because。You get。

 you get one shot to see that area when you move。It can change， and you might not see it。Later。

 next time you see it is changed。 It's not what you have in your prior。 How are you gonna。

Reecttify this inconsistency in what you observed before。And that's your belief。

And what you reoberve and the not， they don't match。So that that's the problem with dynamic mapping。

 I point out in the end of maybe next lecture。三。References that you can look into。

For dynamic mapping in Islam。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_60.png)

So let's start from。Where we where should we start。I shaking the previous slide。T is so X。谁写。And。这。

Is an X also going to be？Something that you're cing。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_62.png)

The question is， are we going to calculate x， no x is given？It is。None， it's we know。

 we know it's value completely。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_64.png)

So， that's why it's。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_66.png)

We say here robot。Positions and orientations are given。We know them。

So anything on the right hand side of this midline， the posterior is given。If it was a Islam。

Meaning that we want to solve for pose and the map， I would write it like this。

But streo like this means that I want to solve for the map。And a robot trajectory。

Using only relative measurements， that's the s problem。Looccalization is， so this is。Slam。This is。

Mapping。Localization is what。Given a map and the measurement， find the robot。Position， so。

If you do it jointly， simultaneously， then we have to estimate both。

Which makes it difficult because if you get an incorrect estimate of any of them。

 it can affect the other one。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_68.png)

So， we don't have many。Places to start。 We only know Beir rule。

We have the total law probability marginalization rule that we use for prediction。

There's another rule for。Taking expectation or prediction， but that's about it。

 So let's start from Bay rule。Because that will connect us to the prior as well。So the beige rule。

 if you remember。Of。And。The X will be。Probability of Z given M X。Some prior。

So this would be the base rule if I just use the static parameters， Well we have this time sequence。

If you remember， that's what the， that's the notation。 we established that Z1。To T。

 this is actually a lot of variables from one all the way to T。So when I write probability of the1。

To， we're talking about the joint distribution of。They want the P。So I can always。Separate。

One of them。And then write the base rule by keeping this particular measurement。To be here。

So that's what we're doing here。Now， the reason we do that because we are after a recursive process。

 So it is in our best interest to keep the latest measurement we get。

And then try to come up with aris that the posterior from previous time will pop up at some point。

 and then we recognize it。Then starting from a prior， we can just reccursively update the map。

 So that's。That's why we write it like this。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_70.png)

So we write down the base rule。And。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_72.png)

We apply our familiar Mark of assumptions。If I know。The knowledge of the present。Time， right。

Then I don't need the history。So I can drop the measurements and I only keep the latest robot pose Xt。

But also， I don't need future time in the prior。I can drop。

The information from future to be my prior。That's how we're going to model it。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_74.png)

Now， the problem is that。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_76.png)

A likelihood like this for something like a map。It's very difficult to model。

Because if you remember for localization。The likelihood is such that it。

 it assigns a likelihood of value。To a measurement。Given some hypothesis for the。State variable。

For example， for particle filter， given each particle is somewhere。

 take that as if it was true as a hypothesis。Then evaluate the Gaussian distribution based on the measuring you get。

 See what you get。 If it the value is very peaked， that's very likely it matches the model what you see from the sensor。

Now， that was relatively easy to evaluate。 But what about the map。

 There are just so many variables and so many possibilities。

So it's very challenging to work with this。 And you may call this forward model， because。

The forward way of just driving it， it leads to this model。

So the idea that you read in the probabilistic robotics book。Is to write down the base rule again。

 for this part。To flip the likelihood to give you something like this model。

Now we call this inverse model because now， instead of Z being conditioned on。

M and X M is conditioned on。ZNx。It looks like the posterior。 However， it only。

 it is only condition on。The observation at time Z and the latest post。 So that's the difference。

There is no need to。Talk about the entire history。Only a time。T。Then we're gonna get another prior。

And some denominator for normalization。So we're going to substitute this inverse model， instead of。

This term forward model here。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_78.png)

So once we subd into the equation， we get something that is a little more complicated。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_80.png)

And there are some。Extra tan。That are hard to compute。 We don't know。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_82.png)

Yet what to do with them。Fortunately。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_84.png)

The map is binary。So we're going to do a trick in the nexus slide。The final simplification is that。

For the denominator， when I have P of M I condition on the robot。Poose。For convenience。

 we're gonna drop the conditioning to keep it， to make it the marginal probability of the map。Now。

 this is not true， because。Where the robot is located right now， obviously is free。

But we're going to give up on that。1， cell information。

We're not going to use that information to update them map。So if we give up on that。

 that makes the math considerably simpler。So we end up with a prior over the cell。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_86.png)

Now， the trick is that because it's a binary variable。You can write down the exact。

Same equation and derivatives by just negating the map variable。 And when you do that。

 you get the right hand side looks like what you had， but M is negated。

There are times that are hard to compute。How about we divide。These two guys。To get rid of that。

If you divide them， you can get rid of。These terms that we have no idea。How to model them。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_88.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_89.png)

So we got rid of difficult to calculate terms。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_91.png)

What's left。Is。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_93.png)

What you see here。Because the map is binary。The negated version of cell I is 1 minus。

Probably of being occupied。Right， so the probability of。Negative of M。

Is basically the cell being free instead of being occupied。You have a question， isn't it？

So the robot is occupied more than。We don't know that。

You're saying that a robot occupies more than one cell。

 maybe depend on the resolution of the map and the robot size。😊，Yeah， well。

 so it this making the assumption。还有你玩者。Based on what you're saying。That's what I said。

 But if it's more， we still give up on that。For a small robot， it's usually one or two。Seves。

But yeah， that's that's a good point because if it's。Car。That's a lot more than one cell。

Do we want to give up on that information？Maybe you start somewhere and then you see what。

 what's in front of you。 Then from there， you keep going and you don't never have a problem， so。

To be a small robot。not man。Yeah， if it's a small map， a small robot is fine if it's。

Like a car on a road or some some。Way of moving that when you see what's ahead of you in the future。

 that's never a problem， because。As you move， you already see what's ahead of you。

 you never need to update where you stand。It might be okay for a static world。It is okay。

 theres a deeper problem， right。Certain question of awareness that the robot is aware of where it is。

 which is not。 But it's not important because I ultimately， all， all of these are。Correlation based。

In France。These models are not slightly conscious。There was some debate on Twitter。

Some neural networks are slightly conscious。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_95.png)

What do you think？

![](img/e29a3be8da83cd7d5c7325fd2d883b00_97.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_98.png)

I am interested in your opinions。One of the only times。😀Yeahは。Yeah。😊，未点。Nural networks。But top。

Numb of poll in a Maryland network。Cancer。Your master idea is that let's look at the topological structure of a neural network and look in the number of holes in the network。

Figure out if his's conscience or not or not。That is very abstract， maybe。It's a good question。

A lot of people don't think it is because its neural network is modeling correlation。

With an input and output， it doesn't understand causality。We don't know what caused what。

 We just know the correlation to map the output。To the closest interpolation and extrapolation of the input。

I argue that people are doing that。Com place。And you argue that。

The networks are getting more and more complicated。If you claim。

That's the Bton and Brusel's argument。 If he claim there is a teapot。En the space。

Rotating around the moon or earth。But it's so small that nobody can see。 It is on YouTube prove it。

It's not a me。 to disprove it。But that's the goal。 I mean， if we can one day。

 we can have consciousness for the robot that's。Exciting and scary at the same time。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_100.png)

So I don't personally think that the consciousness is all。Algarthmic。

 there's a lot of it is embodied， is biological。There isn't any conscious mind in nature， in vacuum。

Because we don't have that。All the conscious。Form of life， they are embodied。In some ways， right。

Whethertter it iss a bacteria。Becausech they're not conscious， humans are conscious。

So if we're the example， we have not seen yet an example of。What's the term unembodied？

Consciousness that's。可以丢人的。嗯。😊。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_102.png)

You can make them take the touring test。😊，But we also only know behavioral plans。Yeah。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_104.png)

Well， if you get a robot call。You might believe that's a human at some point。

That doesn't mean the robot behind the call is conscious。Or maybe it slightly is。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_106.png)

We don't know。But it's pretty cool。 It's a cool topic， to。😊，Think about it。

 So it's not all about occupancy mapping。You can spend some of your time to read about this。

Futuristic and sci-fi ideas， too。 We are interested in these ideas in robotics。

If we don't teach it here， because we don't know how to do it。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_108.png)

That's the only reason。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_110.png)

We're covering occupancy grid mapping today。All right， so。Now， we got the recurs save。Tams。

The first part looks。To be。Only using the observation at time Z。Now。

 there is a precursive part that we wanted to see this。This whole time here。This is the。Poerior。

At T-1， because when you compare it to this term。It is the posterior， just at the previous time step。

So that's what we wanted。 We have a prior term。Wch is good。 We need to start somewhere。

And we know how to start。 There is a probability of 0。5。 We don't know anything。 That's the prior。So。

 get the prior。The ratio， not the probability itself。Multiped by the previous ratio of the。

Poserior divided， but y minus-1 minus the posterior。

 then multiplied by whatever is the evidence the likelihood。From data at that time。

Then you can reccursively update the posterior。 However。

 this is not compelling to work with because we are just multiplying probabilities again and again。

We end up with numerical problems。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_112.png)

In a computer。To to find something that is more compelling， we， we're gonna work with。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_114.png)

Log arts。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_116.png)

So this ratio of probability is called odds。If you've done gambling， you should know that。

So the odd is three to one。On the website slide， can't you。End up dividing by zero。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_118.png)

We might。 Yeah， That's also a good point。 So generally， there are a lot of problems here。

 because if the per is 0。Now， we're not going to pick it prior to zero。

Because you're intentionally breaking on the algorithm from iteration1。But you're right。 what if。

We do have zero at some point because at the end of the day。

 we're modeling the probabilities to go to1 and0。 It can happen。

So it's not compelling to work with a lot of。Numerical problems。 The log art will fix that。

Because then we're gonna to just add terms。So that's the reason you don't see。

This equation anywhere to be coded。You're going to end up with numerical problems。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_120.png)

So， the odd of。Not winning or versus losing， but being occupied for a sale versus not being occupied。

And we take log of that， because log will convert。The product to some。 And we like that。

We can add numbers instead of multiplying them。That would remove the risk of multiplying with a very small number。

And because we only track maybe 15 or 30。2。1632 floating point numbers。

 That will be a problem if you have a small numbers。

And it's also nice that you can always recover the probability from the loggo。

 It's just the inverse of that。 The straightforward calculation will show that。😊，You will get this。

Which this part might remind you the logistic。Bgression。Model。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_122.png)

Because the logistic model gets some function and it will squash it into。

They're interval between 0 and 1 to make it a probability。

Its generalization is the soft Mac that you use。A neural network for multiclass classification。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_124.png)

So log odds， we talked about it， it's nice because it alleviates the problem of numerical issues。

 we can add terms and avoid truncation problems。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_126.png)

Now， the range of log is。From。Minus infinity to positive infinity。

 And that's not a problem because when you recover the probability will squash it。

 that logistic form will squash it between 0 and 1。So based on probability of 0， you have。

Minus infinity。 and one， you have positive infinity。 Now， if you choose something。Like three。

 you're going to get already something like one， right， You don't need to go to infinity。

So you can see something between。-3 and 3，-2 and 2 is the range that you might expect to see these logouts values until the probability is completely saturated。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_128.png)

So if you take the log of both sides， we have this nice formula that the log out of the posterior is equals the log out of the term that relates to。

The likelihood at time T。Using that inverse sensor model idea。Plus。

 every recursive term from previous。Ittereration of the algorithm。Minus a prior。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_130.png)

Because the other two are p over 1 minus p。The last one， the prior is1 minus P over P。

 So that's why it's。There's a negative sign。Okay。The log of。We。What we're doing。

 we're saying the log of X， Y， Z is。Log of x plus。Lg of y plus log of z。

And this last part needs a negative because。To match。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_132.png)

The way we defined the log art was the probability divided what minus probability。

 not the other way around。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_134.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_135.png)

So we are done except that we need to talk about this algorithm because we still don't know how to evaluate the investments or model。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_137.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_138.png)

Before that， this is the algorithm that you might call occupancy grid mapping。You get。

To start with the previous。Belief in form of。Log up。

Current position and orientation and current measurement。发啲。Just as。Prior is constant。

And you might define L 0 to be。Log of。0。51 minus0。5。Log or1 which is 0。

So it can actually disappear if you're。Initial probability for a sale is 0。5。The log order is 0。

The probability is 0。5， but the loggo is 0。It's a prior。Now。

 maybe you start from a map that you built yesterday。It's not 0。5， it's something else。

Then you can consider that as the initial， the prior per per each cell。 Does that make sense。

So we're saying that if the cell M is in the perception field。

 there are many ways you can implement this， but this is a simple。

We are thinking about it for all the map cells。If the cell is inside the perceptual field。

 that means we are currently observing it's within the perceptual field。Update。Their believe。

Porability using the log art formula。Otherwise， don't do anything， just leave it to be what it was。

Now， the computational complexity of this algorithm is clearly linear in the number of cells in the map because of this for loop here。

If you have。Let's say n number of cells。 We have to loop over every cell。

 and we have to check if the cell is within the perception field or not。So in naive implementation。

 it will give it linear time， complexity， assuming that this will take some constant time。对外围。

But probably you loop over all measurements， and maybe you have M beam M beams for the laser。

 so it's like linear in the number of beams。But M can be much smaller than n， probably。

So it's not too bad and you can come up with ideas maybe to just search in a neighborhood in the map based on where you are。

You don't have to loop over the entire map。Then it will make it much faster。That will。

That shows the importance of a data structure， a naive。

Memory assignment for this type of problem is not very efficient。 If you have a good data structure。

 that will allow you to search fast， query fast and update fast。For 2D problems。

 for spatial problems。Qud3 is a good data structure。For 3D， we will talk about aery that we use。

Intruy mapping。This is a data structure that will divide。Each map to four grids。

 And then you zoom in and divide it to four more grids if you need。Otherwise。

 you just leave it to be a giant block。So it's used a lot in different types of。

GO information processing， and it's useful here as well。 The arc3 is the three division of that。

 when you have eight neighborhood blocks to process。KD3 is a general version of。

This data structure is category is not for。Physical spaces spatial places。

 Quad tree and aery are for 2D，3D spaces that。😊，We have data。

 it's more efficient for this type of problems。But if you have a general data set。

 you probably want to look into Kd3。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_140.png)

So what is the inverse sensor model if we know that。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_142.png)

Sounds like we can implement a version of this method。Now， suppose you have a range finder that。

goingIt has multiple beams， but for the sake of visualization and conversation。

 let's take a single beam。This orange line。That's now read。

The problem is a single beam is too narrow。 if we were only。Opdating cells along the beam。

It would take a long time to build a map。 So we might。Assume some thickness for the beam。

So that when it goes through some like this， we end up。Updating more cells， as you see here。

Now to what extent you want to make it thick like this？

It depends on the problem and you don't want to go too far because then it will make it inaccurate because now you're updating the map based on assumption。

 not data。So there is a trade off。Likewise， for the end part， when you observe the obstacle。

You can think about it as a point， Or you might assume well the obstacle has some sort of thickness。

 And maybe I am going to。Cover a little more area。And again。

 you don't want to do it too much because then you inflate the obstacle so much that it might not leave a space for navigation。

So in practice， you can expect to。Spend some time tuning these prompts。

Although there are good initial values in a lot of open source libraries already。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_144.png)

They tend to give reasonable results out of the box。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_146.png)

So you might give them some names so we can implement an algorithm。So， that。

Fhickness that we we're going to consider for the beam is。Parameterized by this beta angle。

We turn a single line to something like a cone。The alpha is。This。

Cylindrical thickness of the observed obstacle area。Now， in reality， this is a point。

 but we model it。 This is an exaggerated version of。

How to model that point that a single being can cover。A fair， fair part of the map。This if it's for。

 let's say， beam J。This is not the heading of the robot。So this will give you a range。And。3。

Bearing angle for that beam。So， from a single return point。If。This is my map， right。This。Now， I can。

Consider range is D。And an angle。Two， the closest beam I have on the robot。

So that will give me a range and bearing。Information。Now we want to know what to do with it。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_148.png)

So if you look at the occupancy graph。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_150.png)

It will be something like this。First， is free。You might hit the obstacle。

Then the probability for that orange region will be high close to the probability being occupied。

For example， this is0。 This is one。 Maybe you consider anything from， you know，0 point。35 to be free。

 Anything below that， maybe anything above。0。65 is occupied。

And then anything in between is just unknown。So， then。

There will be a part that is beyond the obstacle。Potentially。

Your maximum range is bigger than this obstacle， but there's part of the map beyond that obstacle that is occluded。

Because the olude area。Is not observed。We。One updated， that's just a prior。

For some probability that is unknown。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_152.png)

So this is another way to show this idea。Now let's put it in an algorithm。The last slide is R。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_154.png)

Yeah， I think so there's a。Are you talking about the algorithm。That I just moved to。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_156.png)

Most of bar too。Where is our。By the ZT。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_158.png)

Oh， yes， I think so。We should。不。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_160.png)

We're talking about this are。Yeah。I think it's the first time I'm seeing it。Is that the same？



![](img/e29a3be8da83cd7d5c7325fd2d883b00_162.png)

I think it's alpha it's not R。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_164.png)

So this is talking about thickness around the occupied point。I think。Right。So these is the。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_166.png)

I have to fix this。So， let's leave the。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_168.png)

And。No， Z is not D。 We'll see Y。I'm just going to leave it like this。

You have to go through the algorithm because D is what you predict。 It's a predicted measurement。

Z is what you actually observe。We're interested in。Theirre mismatched to detect if。

That's the cell that we should update or not。But this R， I think you're right。 This should be alpha。

 right。Because。We are assuming a certain thickness for the。Obstacle。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_170.png)

Now， that is a problem because it's not like the obstacle。Is completely observed。 If it's a table。

And you see the leg。Maybe if the robot moves。You still hit the table。

So theres a lot of room to make the map richer by maybe cameras and other information。

But the basic idea is that I see an obstacle。 I assume some thickness for it， regardless of。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_172.png)

What's going on in the real world？

![](img/e29a3be8da83cd7d5c7325fd2d883b00_174.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_175.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_176.png)

So the algorithm works like this。 I want to。Ultimately， return。A log odd value。Not time T， based on。

Current knowledge of the robot pose and observations for the map cell， I here。

So what we're doing is that consider the center of mass of the cell to be X I and Y I line 2。

Calculate the range and bearing。Relative to where the robot is located， that will give you。R and P。

Now that， you know， the angle。Of the map cell。In the robot frame， sensor frame。

 find the closest beam because we might have multiple beams。

With fixed resolution are located in the sensor， find the closest beam on the sensor to this particular cell。

I'll talk about this two more for now。We get the range and bearing of the cell in the sensor frame and the robot frame。

Using the bearing， we find the closest beam from a multi beam sensor if it's a single beam。

 of course。There's only one。This argument means that just loop over it。

 see which one is the smallest。Right，Because if the map cell in the sensor frame is located at。

 let's say， 30 degrees this side。And I have beams at like 25。15，0，15。25。

 then the closest one is the one that is at 25。There is no beam at 30 degrees。

So we need to find a beam that is available on the sensor。Okay。So that's the closest beam。 Now。

 we work with the range， if the range。Are that。Nice change to our。This is the same thing as D。

If the change， if the range are that we predicted for the cell。With respect to the robot pose。

Is bigger than minimum of the maximum range。And the distance you observe from the sensor。Or。

The angle is bigger than that cone that we constructed。So， this is saying that。

If the measurement is telling you something that is more than the maximum range， that's impossible。

Because there is a maximum range for the sensor to operate。

 This minimum ensures that you respect that physical constraint of the sensor。If it's not maximum。

 the minimum， obviously， will be the measurement plus half of that alpha thickness。

 So take the minimum to make sure you respect the physical constraints。 Now。

 if the predicted range for the cell is more than that， that means the cell is not in your。

Perceptual field。Or if the angle between the closest beam and the relative angle of the cell in the robot frame is bigger than that cone。

 half of that。Beta value for the cone。 Then it still is also not in the perceptual field of。

The closest beam to that cell， in that case。The sell。Should not be updated。

 and we should return the prior。Value。Else。If they return， Z is。Less than the maximum range。And。

The difference between what we predicted for the cell and the actual measurement is less than half of that alpha thickness。

 That means we're dealing with an occupied case。 Then return a log out that is for occupied。

If this is also not true。And the range is less than。

Predictive cell is predictor cells range is less than。Measurement Z。

 it must be free because all the cells along the beam up to the obstacle are free。

 That's the negative information that we get from。😊，Arrange finder sensor。Negative。

 because the positive information is that it's occupied。

 We don't directly get from sensor what's free。But we can easily infer that anything up to that point must be free。

Unless it's a glass。For a laser。It is not that easy。 Birds run fly to the window。

It is a problem in nature， too。Don't blame robots。This is a harder problem than it looks。Now我。

two questions might be。Where do you get these two， Well， I just mentioned that you might assume some。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_178.png)

Threholding probabilities。 And then use this 0。35，0。65 to get the logouts。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_180.png)

So L。Will will be。Log of。1 minus-0。65， whatever it is。To you pick。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_182.png)

The these thresholds， and then。Your investverse likelihood model is just drawing， is fixed。

Acccuuppied， and unoccupied。Log odds based on this logic。Now this is just an idea， right。

 it's been successful in practice。 You can modify it， in many ways。😊，And people have done that。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_184.png)

![](img/e29a3be8da83cd7d5c7325fd2d883b00_185.png)

And for the robot just quickly。 So imagine you have this X， Y， and then you have a robot。

Looking somewhere。And then you have a cell。The robot has this heading。

And then you're going to predict a range。92。You're going to predict the range R。And also。

Maybe an angle。With respect to the horizontal axis。 Now， this angle is。A tangent 2 of Delta Y。

Over deelta x。Acangent 2 because we want to get an angle between minus pi and pi。Delta x is。

Delta x is the map coordinate。ALong extraction， minus the robot。Hes x。This a robot position。

And headache。Similarly， Delta y is y I minus y。2。But we know that we should subtract the robot heading because we are actually after this deelta here。

Right。We care about the relative angle of that cell。So hence。

 you see that phi is this arch tangent 2 of the deelta Y and deelta x minus the robot heading to compensate。

The robust orientation。Now， if that's not accurate。

 you can expect that you get all sort of drifts over time and inaccures。

 That's the importance of known and。Perfect knowledge of the pose to get a consistent map。

So that's the initial calculations from line。2，3。You see here。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_187.png)

So。Now we did all of that， you have the algorithm now， you have theInvest sensor model。

You can read the laser data， assuming you know the robot pose。三号。

Although there is a way to run part of your filter as you build a map， and that's called Fast slam。

And it's known as G mapping。Package that you see in Ross。 That's what it's doing。

It builds the map and runs a particle filter in the map as you build it。It works well。

 It's a very nice work， but it has a scalability problem because you can't use so many particles because each particle is tracking its own occupancy grid map。

It's going to be very expensive if you use a lot of particles。

But it is a very successful and useful package。So if you know the pose， you build。From laser scans。

 that you see here， we can build now this reconstruction of the environment as an occupancy map。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_189.png)

This is an example of the third floor of MI IT C sale building。TheyMove the robot。

People do it here all the time as well。I just don't have an image。We have3 map of this building from。

Some of our research。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_191.png)

And a lot of you have done this maybe in Ro 550。I don't know if you took the robot out， but。

You have done probably something like this。So you send a robot and now you can map this。 Now。

 if you have this map， you can actually later load this map and run a particle filter in it。

That's what we talked about in。The localization lecture。Your likelihood will be different， right。

 You do rate racing together a range， and then you have an actual range for each beam。

You get the innovation and then update the weights。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_193.png)

So this covers the other side， which is the mapping part。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_195.png)

Now， to summarize。This is。I would say this is the first method you should learn， if you want to。

Start looking into robot robot robot mapping problems， dense reconstruction。

This is in the context of robotics。 It's not in the context of computer graphics。

 You can make a lot of nice。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_197.png)

Reconstructions， but you， you might need servers and。Offline calculations。

 these are algorithms that we care we can run under robot。So they've been very successful。

 If you have robot poses， it's relatively straightforward to implement this。

 And I do give you an example of that in the code folder。😊，There's a mapping folder。

You have an example of it using Intel data。 There's the Intel Research office in Seattle。

 There's a data。The code is building a map using that。

So cells are considered independent next time we want to relax this assumption。First。

 we want to come up with a better way to perform the inference such that we get the variance。

For each cell， not just the vability。We also want to relax at an independence assumption。The recent。

 I mean， this is an old idea to learn。These probabilities， but。There are a lot of research out to。

Use machine learning also to boost these algorithms to perform better。

What we will talk about is it is Michel learning style of inference。

 but it's the kernelnal method version。 It's not deep learning。Because it's a kernel method。

 And it's。Straightfor to implement。 still it can be online。 You don't need any offline training。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_199.png)

That's what makes it attractive。

![](img/e29a3be8da83cd7d5c7325fd2d883b00_201.png)

To read about this， you can read Chapter 6 for the range finder sensors。 And Chapter 9 is all about。

Occupancy grid mapping imperuralistic robotics books。



![](img/e29a3be8da83cd7d5c7325fd2d883b00_203.png)