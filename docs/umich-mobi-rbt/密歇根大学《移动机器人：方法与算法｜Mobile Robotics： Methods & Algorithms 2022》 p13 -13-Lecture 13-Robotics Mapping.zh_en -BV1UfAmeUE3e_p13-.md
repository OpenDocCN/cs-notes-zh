# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p13 -13-Lecture 13-Robotics Mapping.zh_en -BV1UfAmeUE3e_p13-

In this lecture we talk about。Robotics mapping， this is a second lecture。And this topic。Previously。

 we covered。Occupancy mapping。 So in the last lecture， we learned a basic method for。

Reconstructing a 2D scene， given rangefiner observations。From a moving robot。

And we talk about it that ideally you get the trajectory from the ground truth。

 but because we don't have that， you might run in the slam algorithm， this is an example of Po graph。

So， each note is。And robot Paul。Because we construct this trajectory at discrete time of steps。

 that leads to a graph， each note is opposed at a particular time of step。

And then edges shows the connectivity of this trajectory。So， the red edges are。

Conive movements of the robot， green edges are called loop closure。

This is a topic for this is a conversation for the Islam lecture。

 but loop closures are when we revisit the same area。

 we establish some geometric constraints between existing nodes in the graph。

 and that will make the graph connectivity better and that will help our estimation results to be better。

So theoretically， the more revisiting and edges in the graph， we should get better results。

 we have more information。Now， we solve this trajectory and at every。Point， the robot observed。

 maybe some。Range measurements， right？ And we use non poses and observations to reconstruct this map that you see under。

Right hand side。SoAnd we call this the occupancy grid map。

Here is an example of occupancy grid mapap using a real data set。

The data set is called the Intel data is collected in an office in Seattle， it's a research lab。

 so a mobile robot is moving along the hallway several times and goes into some of the rooms。

It's equipped with a 2D laser range finder。We use the same algorithm that we talked about to build a map。

After solving this s and getting the trajectory。 and then we can reconstruct the。Floor plan of。

This building for one particular floor。This is just an example of。Applying that method to real data。

Now， what happens is that。Ideally， we would be able to reconstruct。The floor as is。

 but because the observations are noisy。And spars。We do not have。

Continuous observations of the structure。 We just get sample points。

Based on the resolution of our laser range finder。So， we end up with。

Incomplete maps or partially completed areas。So because of the noise and。

Types of objects that we might see in the environment。 Maybe it was transparent in this case。

 and the laser was going seeing through it。So we end up with incomplete parts and sometimes also areas that are very difficult because there's a wall。

 but also。Then there's free space， then there's a little wall。

 so these are inconsistencies in the map。 it can be caused by the error in the localization。

 or it could be because of the inaccuracy in the range measurement， depth measurement。

Our goal is to make this a little better。It would be great too， if we could solve it。

To be exactly like the real environment， But that's。It's proven to be very difficult。 So gradually。

 we have better ideas to make it better。Now， this idea has been extended to 3D。So today。

We do have a library that you can run on your robot and build 3D occupancy gridmap。

The name of this library is。

![](img/cd54da0d254f7f71c758101845203162_1.png)

Octam。So octamap is a 3D version of this 2D map that we discussed instead of grid cells。

Now we talk about volume elements that we call vels。 These are cubes。Instead of grids， we have now。

Cubes， we call them voxels。So these volume elements。Or vox cells。

Are a way to reconstruct the 3D scene in a discretized way。So if the voxel size are very large。

You get the course map。 If they're fine， you can start seeing the map。To be looked like。

 to be similar to the reality。But that becomes very memory intensive because the。

 the amount of memory you need to reconstruct at 3D it will grow exponentially as you add an extra dimension。

😊，So that is a problem， for example， the logo is this 3D。A tree， that you see here。

 there are some examples。I believe these are from real lighter data。 So if you have not。

 you have your trajectory and you have lighter。Measurements。

You can use this library to reconstruct the scene like this。Now。

 this does not solve any drawbacks of the 2D problem。

 This is just an straightforward extension of it to 3D with very good software engineering and good use of data structure。

And an easy to use API。I was curious， does it ever happen Ly？Your entire。A single box of size。Yes。

R of offices like in the same way。Evens have their her population is not as precise as their thing that they're looking at front of them。

So is there anything link？The thing that you're focusing on。

 you can have really high resolution that you。Have to care about everything else you know。

Higher for you of larger size boxes for that stuff。The question is。

 can we have a multi resolution map？Where we have。Find a resolution in regions that maybe we care about。

 or maybe we observe。More frequently， more often。And having large voxels for areas that maybe we don't have any observation or maybe we wantan to pay less attention。

 for whatever reason。Yes， this mapoctomap is like that。 So the ay data structure。

Is precisely designed to do that。Initially， the structure is。Well， this is a tree structure。

 So the tree structure will。Grow like this， right， If it's a binary tree。But this is not binary。

A 3D space。 So it start with a giant box cell， and it divided to。How many。You get two。

 You do another one， you get 4， and another one， you get 8。Hence， aery。

So you get 8 vill after one division。 So each parent will lead to。1，2，3，4，5，6，7。eight。E children。

NowIf you want to do one more， you don't have to do it for every new v。 Maybe you decide to only。

Do wait for this one。So that makes it。More flexible。Probably here。

 there is really no need to divide the space。 This is free。One block is enough， right。

 And then we see the leaf note， leaf size。So what is the depth of this tree that you want to explore。

At most， there will be the smallest vel you will see in your map。So that will split your space until。

The smallest division， for example， here， has， let's say， a voxel size。Of maybe 0。5 me， right？

That's your。The size of the leaf note。So it is multiple resolution and。

Adver is that important problem if you don't do this。And naive just vization of the 3D space。

 it will be more intensive because。We have to。And tired that。

This createize the entire area that we want to map into tiny voxels of this size。

 and that's very inefficient。So that's the importance of using data structure。

So but whether 2D or 3D， they share the same problems。They are。But approach。

 theyre computationally efficient because of that independence assumption。

 the probabilistic reasoning was for a single grid or vel。And that makes it very fast to implement。

And they， they are relatively easy to implement。And we do have 2D and 3D software。Now。

 the problems are that they grid。Assumption makes these voxs statistically independent。

 So we are not able to exploit the existing correlation。And the environment。

That means if you have a sparse point cloud that will leave holes and gaps in the。

 in the map and the map in France。Boycon is incapable of。Completing the scene。

It can only complete where you observe。 It cannot interpolate between two points。

 two boxes that you observe and filling the gap。So having that predict predictability feature in the map to be able to complete。

At least small gaps in some regions is a desired feature。Now。

 that becomes very important if you're operating in a large scene。Lidear point class， for example。

 when you are at a close distance， they are dance。But as you go far 100 meters away。

 suddenly they're so sparse。 They almost seeing nothing。

So even though the sensor has a very long range。Because these beams。Pravel in form of a cylindrical。

Space。They expand quickly， as they go far。And that makes it a challenge to reconstruct the scenes for far distances。

Bless you。Do you have COVID or regular flu？Hope I have taken three COVID。会。Well。

 I'm glad you came to the class while you're waiting for the results。hu。Don't worry， guys。

 took the test。We'll see。hu。No notion of map uncertainty。Now。

 we fill in the v cells with some probabilities， but we have no idea how uncertain or certain we are about that region。

Because the way the inference was working was directly calculating the probabilities。

 The problem is these probabilities get saturated after a few observation to  one or 0。

 depending on the log odds that we choose。And remember， those were tuneable。

 Maybe you choose something that after one observation it gets。Really close to 0 or1。Now。

 then we don't have this idea that how uncertain I am for different regions。

 And that means that we need some notion of variance， variability for that region。Now。

 why do you need variants？Well， because the second order information like covariance of varianceance is important。

 imagine a car is moving in on highway and you。Detecting that。Car moving in front of you。

 if you measure the car one time to be 1 m away， and the other time is 10 m away。Where is it。

The variance is super large。The average is 5 m away。 The reality is， it's。Maybe it's not5 m away。

 Maybe it is1 m away。So there's a really large uncertainty about that situation and makes it really dangerous because。

Which one do you want to believe was was a 10 m outlier。Or the average is correct。

 So the mean is very unreliable in some cases， if you just want to look at that。

So the mean is the location。Imagine a Gaussian distribution， the variance is the scale。

 how certain we are about that location。So if we know the variance is large。

 then we know that we lack enough information to make decisions based on that。

And that will improve our knowledge of that。Area that is mapped。哦。

So if we do construct maps according to uncertainty。

sensoror measurement update that we make does it make sense to then construct our map up based on the mean but late？

But any obstacle that we want to avoid is that constructive advisor。

 just this away from needs dictated by the variant， so if you're very uncertain。

A gigantic problem on your map then becomes an area that you don't want to。Nviate to or。

This is still this information that we retain from many sort of like Asianian updates still。

 does the map still constructed according to the mean and that we just？

I have more risk associated with it。So the question is that。

 are we going to build a map just based on the variance or uncertainty or we still need the mean when we run the inference？

We still need the mean meanan is what you visualize and you see。The occupancy or the semantic label。

The variance will give you another。Map， you can visualize it。 Of course。

 the robot does not need the visualization。 The visualization is for us。And。That variance will help。

Algorithms in planning and decision making。Now， if your map， for example。

 is modeled as gaussian distribution and you're going to plan based on the。

Information in each region。So the entropy or the amount of uncertainty information。

 it is only a function of your variance。 It doesn't depend on mean at all。

 So depending on how you model it。It can change， but generally speaking。

 you want that variance for decision making。That can be exploration。

 that can be deciding where to complete the map。And。It could be the application something like。

That highway example， maybe you're tracking a local map to track objects and you want to make decision based on that。

So decision making based on the mean is a bad idea。It's unreliable。

So we need an inference method that is capable of。Infering that distribution so that we can talk about the variance。

This occupancy mapping method， by construction is incapable of。Giving the variance。Now。

 another problem is that the map has a fixed resolution。 When we build it。

 there is no way you can increase the resolution， because the data is。Consumed。Turned into。The map。

 the vulnerabilities。And there isn't any way that we。Can increase the map。

Without going back and starting from scratch。RightSo once you build a map， the information is lost。

 the informed of those probabilities， and we have we cannot increase the resolution。

So when you say fix back。可。If we talk about how it's like essentially a slightly variable resolution and that as you get more information。

 it kind of increases the resolution up a double saturation point。

 but is this essentially saying that that process of the variable resolution can happen during mapping itself。

 but once that's done， you can't do anything about？So the question is that。

 is that fixed resolution related to this multire？Now。

 whether you can do this build this hierarchy of building multire map or not。The leaf， size。Is fixed。

There is a discretization parameter， and that is fixed。

What I'm talking about is that what if I make it continuous infinitefinite resolution。

 you can query anywhere you want。At any resolution you want。At any time。The question is。

 is that possible？So there there should be an underlying model that is continuous and that continuity allows us to query。

This material resolution here doesn't create discrimination before we start mapping。

During the process of。The thisritization。Happens as we receive data。So， another question is that。

 do we decide about this multire of the areas beforehand， No， we start from some。Parent knows。

 maybe some rough。Very coarse discretization。 And then as we receive data。

 the algorithm will dive into each blocks。 So this aery will have different blocks in the environment。

And then， each block。We。Can find a block And then where the measurements are falling in。

 And then at that point， we will decide if we need to split the。Resolution。Yeah。

And within each block to query these voxs very fast。 We can use voxel hashing。 We can use。

Map data structure， and see plus plus。To use hash code to access them in constant time。

But to query the block to know what block we're gonna operate， that requires a search in this tree。

 and that will cost。Log in。Similar to Kd3。We have to pay the cost of log and to find which block we're following in。

 and then within each block is constant time because of hash table。So now our goal is to。

Address these three。We want to。At some level of correlation in some neighborhoods of age。

Vox cell or sell。We want to have the notion of uncertainty or variance。

And we want to make the map continues。Let's go back and revisit our Bige rule because our map was using this。

We started from Bee。Just to review， we have a hypothesis here， the map。

Or the probability of each cell being occupied or not， given data。There was a likelihood model。

 probability of data， given the hypothesis times a prior。

Over the hypothesis divided by some normalization constant。And what we did。

 because the forward model， the likelihood was difficult to model。

 We did a trick of defining in sensor model， and。Refining log odds and all of that。Now， in this case。

 we're going to use。Another idea that leads to a very efficient inference method。

That will also give us the variance。And that's based on the notion of conjugacy in the statistics。

If the posterior distribution。Is in the same distribution family as the prior。

Then the prior end postor are called conjugate distribution。That means。If your prior is Gaussian。

And your posterior Gaussian。Then there is a choice for the likelihood function。

That will allow you to have this conjugacy。Gassphian prior， proper likelihood。

WShe is the conjugate for the prior will give you another Gaussian posterior。

So the key is that because we know the distribution of the posterior。

 the problem is reduced to finding its parameters or hyperparmeter。

The general problem in Bay inference is that we don't know the shape of the posterior。Now， suddenly。

 with this way of modeling， we know the distribution of the posterior。

 we just need to find these parameters。And that makes it pro done。

This brings a huge algebra convenience and is computationally very efficient。 Otherwise， in general。

 we have to do integration and all sort of inference challenges that。We've seen here， and they are。

 they generally exist in。Misal learning。And。Other related areas。Now， the conjugate distribution is。

So you can read about it here。So it's a special case of seeing Bayes rule when there are particular distributions that when they interact。

 we can know the result。Now， there is a table here。 What is conjugate to what。

We will use this Bernoli likelihood and beta distribution for occupancy mapping。

 and we'll talk about it。For semantic mapping， we will use d La and categorical。And for example。

 for a normal distribution or Gaussian distribution， its conjugate likelihood is， again， Gaussian。

 That's why even in your， in your homework。The first one。

When the question was solving a Bayesian inference problem， the prior was Gaussian。

 The likelihood was Gaussian。 You just multipplied them and derive another Gaussian。 Then you。

 you use this conndjuac C。Somehow you proved this for two Gaussians。

 you could derive another Gaussian。So this is a generalization of that rule for a variety of distributions that we know they work that way。

So it's not the case always that the prior and likelihood must be the same。

 Some prior and likelihood have this conjugacy that the posterior will be in the same form of the prior。

So the beauty of that is that the next time when the new posterior will become the prior。

 we can reccursively just repeating this。So if I have a measurement that the likelihood has conjugacy with some。

Prior distribution。I can， reccursively。Wun this update in closed form。And makes it very efficient。

So this is a non result in the statistics。 we we staians notice。

What it turns is very helpful for us in the context of mapping。这在在什么广这个间。我し这个分是る。这个。前进。question is。

 why didn't we use conjuation the extended comma filter or kman filter？We don't know the post。

 We're trying to。Estimate a Gaussian approximation of the posterior。Here， by construction。

 we know the posterior。 So the previous way of estimating is that I am given some data。

And I want to come up with an estimate。 And part of the model in choice was that if I go with an extended common filter。

 I can track the mean and covariance。 That will give me an approximation of the posterior。

By no means， they must have the similar distribution。And sometimes it might be a very bad idea。

 but here。The framework by construction is such death。We know the posterior shape。 Now， again。

 whether this is a good construction for the reality or not， it depends on the problem。

 for this problem， we will see why this is good。So the Gaussian distribution is a conjugate prior for the likelihood that is also Gaussian。

For example， if you want to map for substance concentration。Then， we can use。This type of。Mapping。

You send a robot。 you want to monitor。 You want to measure the concentration of a gas， for example。

Maybe it is a gas leakage somewhere。You send a robot to monitor。

Maybe you have a sensor you can measure the intensity in some small area around the robot。Now。

 one measurement is obviously not good。 You want to move around， collect。

 collect as many measurements as you can， and then reconstruct。The distribution over。

The spatial area， the area that the robot is exploring。Then it makes sense to use。

A Gaussian prior may be Gaussian likelihood。 And we can keep adding information to each v cell。

To model the concentration of that substance。 So in environmental monitoring task。

 this can be helpful in the context of。Occupancy mapping。We're dealing with a discrete case。

 We already know that。A cell is occupied or not， so that that makes it binary。

So Bernoli distribution， Bernoli likelihood is for the binary case。But what is the prior posterior。

That's what we we need to look into。Better distribution。

Somehow we are informed that there is such a distribution in the statistics。

 It's called beta distribution， what it does。It places a probability distribution over the probability of two events。

2 events here being。Probability of being occupied and the probability of being free。

Depending on it has two hyperparmeters。Or parameters， alpha beta， based on different values。

 it can get different shapes。

![](img/cd54da0d254f7f71c758101845203162_3.png)

Now there is an animation here。So when this alpha beta changes。

This distribution can switch between event 0 and event 1， right。We have two events。Each side。

And at this curve。Its telling us how much of the mass of the distribution is。

On which event in a continuous way， because。It's not that。It。

 it's bimodal and switches between events。 It continuously distributes a mass。 Now， if it's half。

 that means that both are equally possible。 and that's where we don't know if it's occupied or not。

Rightright。So when it's be curved， you can imagine that's probably our prior when we start。



![](img/cd54da0d254f7f71c758101845203162_5.png)

Now， what's the。Equation for this distribution。So you see that。Last line in this equation。

 there is a normalizing constant。 you can ignore that。Then。It says that。X， X is the event。

Here is being occupied or not。So it's occupancy。Raise to the power of alpha -1 times 1 minus x times beta -1。

 So that's just the shape of that distribution mathematically。 So you knowing alpha and beta。

 when you evaluate this at。Different。Places between 0 and 1， right， One was occupied。0 was free。

 We get different ways for this likelihood and different alpha and beta will give different shapes。

 So this seems to be a reasonable。Statistical model for。

The prior and posterior to define the occupancy because we know we're dealing with a binary case。

Now the conjugacy comes in when we choose a likelihood that is Bernoli。

A beernoli likelihood is a probability mass function。That it gives you a probability of P。

Let's say if the event is。One is true。And it gives you another probability， which is 1 minus P。

 if it's false。You toss a coin， right。You get and head and tail。

You can model that the measurements of tosing a cone using a betternoly。Distribution。

Which in the limit， you expect it to be 50，50。 if it's a fair， if it's a fair coin。

Can you model a dye with benoli？No。Why not。对对。Yeah。So we have six possible states。Not two。

 It's not just occupied， unoccupied。And Bnoli is seems to be not sufficient。

 We need something more general， And we will see in the categorization， scene segmentation。

 we need a more general form of that， which。Is just the straightforward generalization of this idea。

That's called categorical distribution。 So it's not just two。It's not binary。It's categorical。

 There are K possible outcomes。So with this choice of modeling。

We're going to go and model occupancy maps。Later。We generalize beta to dle。And there are no to。

cateategoorical。There is late distribution。Is the generalization of that beta distribution when it's not just two events。

We have more than two。Now， it's general。 It doesn't have to be three。

 although the visualization is for three。We can have arbitrary number of outputs。Now。

 if this arbitrary number goes to infinity。Then it's continuous。

 And that's something that is called thele process。Well that's not we work with。In this case。

So we have- now you can imagine a triangle。We have three categories。

Then the mass of the distribution。Is such that it， it shows the amount of weight on each event。

If it's equally distributed， that's。That makes them equally valid。As you can see， different shaating。

 or maybe it is concentrated around one particular event。

And we will see how this comes handy when we want to talk about semantic mapping。

The categorical is the generalization of the Bernnodi distribution。So in this scenario。

 instead of two probabilities of P and1 minus P。We have capabilities。

 but such that some of them will add up to one。Right， so it's a discrete probability。

 and needs to add up to one。And。The reason。We will use this probably， because it also models。

Something that we call one hot label。 So the labels。The video weight are0 and1， the measurements。

The segmentation that we do。It's。Telling you is either occupied or not， right。

 The point that you read from the laser。There's no ambiguity。 If there is a measurement。

 you know that's an obstacle。Ignoring that maybe there are outliers。

 maybe they do some filtering and the raw measurements and so on。

So you label it there as occupied one。And then， the probability that。

That particular measurement is free。Or belongs to any other category is 0。

 So the sequence of labels will be all zeros unless for one particular category that you。

Think that's the measurement from。 That's called one hot。Encoded label。Yes。

We'll talk about that again more when we talk about the semantic mapping。

So the result that this setup will give us will enable closed form and。Recursive Bayesian inference。

 When you hear Bayesian inference， that means we infer distribution， not just a point， a mean。

This is an example of a map that we can build。It's here on campus。

 This is the around the way field behind the aerospace department。So the Bayesian in France。

 we are conjugate prior。If we formalize it， it's like。This。

 the first part is that we have labeled that。Or in this form， assuming we have K categories。 Now。

 when I say categories。You can think about。Maybe sidewalk is category1， grass is category 2。

 wall is3。Trees are four。Somebody walking here in red， maybe you call this5。There are more。

 but we just don't see them here。I think on the actual robot。

 it was something between 10 or 20 categories that we could map。But it was fixed， the robot。

 And that's the problem。 The robot would not be able to add a new category on the fly。

That's a big problem if we can solve that， then we really have the next generation of。

Perception in this area。你一直 have。We can。 The question is， do we have a default category。

 It's always a good idea probably to have other or default category and。And。

Whatever we are uncertain or doesn't fit in the other one through that category。

All of these categories now， the visualization changes a little bit in 3y because all of these semantic categories。

Are occupied。So even that default or order will be occupied。 We just don't know。

What concept to assign to it， The robot is not familiar with that。

So it reduces that other or default will reduce to the occupancy map because if this was the occupancy map。

 all of these categories will be just occupied。So it's just free and occupied。 And in 3D。

 it's just hard to visualize free because you won't be able to see the map。It got implementation。

Ex the resolution of their power。Question is， do we use the categories to decide the resolution？

I believe we don't do it here in this resource that I show you， but it is a good idea because。

Sometimes based on the what what you observe， maybe there is really no need for fine resolutions。

 That's a good idea。Now you're immediately thinking that how can I use this categorization to do more。

 And that's basically the idea because the map is suddenly so much richer。It's not just occupancy。

 We can assign concepts， and that concept help so much for the robot to decide。 For example。

 we were task the robot to walk on the sidewalk。 Don't go on the grass。 Stay on the sidewalk。

 do a loop。Autonomously and then build a map。We have a video， we can talk about it more。

So back to the devations。So， we have。K categories in general， they must add up to1。

And like each of them。It can be only 0 or1。 So that means there's only one of them that is one right。

 with these constraints。Because they add up to one， and they can only be 0 or one。

For any map vox cell。We want to estimate this。Vector of probabilities。 So we have K。Pbability。

 So we track one probability per category。That's what we did before as well。

 We had probability of occupancy because it was binary。 The other one is1 minus。Occupancy。

But because we have K categories， now we have to track one probability pair。Category， but， of course。

 they need to add up to one。 The degree of freedom is K -1。 It's not K。

If the likelihood is categorical。Even the。Promted that we want to model。

So the probability of data given the hypothesis， which is the likelihood。😊，It's just the product of。

Please。Fal values。Raised to the power of their measurement。 Now， because all of them are0。

 except one of them。This， let's say。We have a measurement of category 3。

 This will basically will collapse to。This， right？ So the likelihood is this dis fancy way of writing。

Makes it consistent that when we。want to evaluate， it will return the probability of。That category。

If that is the observed category。And if it's not。It won't contribute。 So that that probably won't be。

Won't appear here。boy的。我他。It seemed intuitively the category。I'm sorry。

 the theta vector makes sense in terms of your measurements。

 you have the probability distribution over each measurement。Not really understanding why theres a。

It's just one hot encoded for the measurements for each category。

 The question is why one hot encoded measurements， What if we get。

A vector of probabilities as measurements。The answer is that this is more convenient。

We can get the a maxax of that vector probability in。To these driverss if。

We want to work with capabilities。 We need to。Then the categorical likelihood won't be valid。

The conjugacy won't be valid。Then we have to look into different models。 It is possible。

But that will be a generalization of what we talk about。So this is a simpler case when we。

 even if we get the output of the soft max layer of a neural network， for example， for segmentation。

 we take the arc max of that。To。Turnned it into a categorical measurement。Okay。

 so is this essentially like an。All。We're describinging that。If， if。

 why the measurement comes in form of。Probabilities。We。Take the arc max to see which one is one。

 and the rest are 0。Right。We turned them into decisions。 They hard labels， instead of soft labels。

So that's the likelihood that thela distribution has。

Which is the probability of the parameter or posterior parameter。Given。Data。This is prior。

 still don't have data， but this is just to emphasize。That there are some hyperparameters。

 and that's how we are modeling the distribution。So given alpha as hyperparmeters。Hyperparmeters。

 because they're not theta。 Theta is actually the parameter。Alpha is the parameter of the prior。

Then we call it hyperparmeters to make sure it's clear that。We're not talking about。These。

Outputs that are parameters。Okay。So the richlate distribution has a normalizedizing constant that you can ignore。

And again， it's the product of all categories raised to the power of alpha。K -1。

That's how it's defined。So the posterior from the conjugacy， we know that the posterior。Which is。

 of course， proportional to the likelihood times the prior。

 We also know that it will be a drilllet distribution。So once we know its hyper parametersmeter。

 new alpha values， there's no ambiguity how to reconstruct the whole distribution。

We can look at the shape of it， and we know they're on normalizing constant。

 and we have the full solution。Now， a direct calculation by multiplying the categorical。

Likelihood times。Tle prior， it shows that。We just multiply these theta values。

 and their power will be raised to。Alpha plus y minus-1。

So we learned that if we have a rich sleep prior and do an update this way using a categorical likelihood。

We just can't。Numbers。We're just counting。The number of measurements from that category that we observe。

It is simple， we can discount。And you can define the sum to be like this。

 And if you go back to the Wikipedia page， we can show that。The expected value and variance。Or。

Possible to derive in closed form。 And it's very simple。

 This mean is just saying that divide each alpha by the sum of other alphas。

That will be the probability of that category。And the variance has。This form， you see here。

 So we are able to talk about the mean and variance for each category。😊。

Does this mean that like if you want to add？就发生在电。Can update your past possibilities。Good question。

 The question is that what if we want to change， Because right now， what we're talking about。

The number of categories， this is。Constant。If this。If you want to make this variable。

It might create some conflict with what you observed previously， right。

 and it might create some inconsistency with how we。Integrated past information。

We are not doing that and that is an open problem。I think we could come up with clever ideas。

 but it's。Keep in mind that we want to also do it。As the robot operate。

 I think it's O to solve the problem ofline because we want to understand it。

But there is also a really hard challenge to change these categories as the robot observing the scene。

Just understanding that part is the open problem。If you do know that from the observations。

 then that makes it so much easier。 Okay， The core challenge is that the robot does not understand。

Maybe that particular category， because the perception system is probably incap people of detecting that type of object or category。

So current， at this point， we。P a maximum set that we。No。

 and we can handle and we just operate with that。 So if it's less than that， that's okay。

More than that it's a problem。Now， if K equals 2。That will reduce to。The occupancy case。

 the categorical will look like the Bernoli likelihood， the binary likelihood。

 and the Jewish slave will be reduced to。Beta distribution。So that's the inferences。Not too bad。

Much better than an imvariant。C and filter。So we call this counting sensor model， precisely because。

We're counting measurements for each category。 so that's the name for it。

If we build an occupancy map of the same area。Using this method。Now。

 we still need to implement an algorithm that。Loop overs over map points and see if they're in perception field。

See if that cell must be updated or not， but we covered that already， right。

 The part that we're going to replace in the algorithm is how we。

Update the belief or probability for the map。So the occupancy map will give you the mean。But also。

 the variance that you see here。The variance is relatively higher。And。Areas that are incomplete。

So if a robot wanted to explore， we would know that we should go to areas that they have higher variance。

That could guide your decision making。Now， we， the original data set is not semantic。 Last year。

 Cythia， my PhD student。Segmented this data set for you。So the way she did it。

 she decided that if the robot box。Not walking。 It's the real robot。

 If the robot moves in the hallway， this is one。Segment of the map。

 So all the observations that the robot observed by moving along the hallway。

It's this blue dark blue category。The room in the east， west， north and south。

They have different colors， the center area， it has a different color。

So the robot starts from this green。Rectangle， goes around， explores and comes back in the end。

It's the same place。So on the left side， you see all in this figure， you see all the point clouds。

 2D point clouds with their categories。So we turned an occupancy data set into。A semantic data set。

 it has categorization。This is a good toy problem to test our。Semantic counting model。 Now。

 if you use more than two categories。What we will see is that the free space is， of course。

It's own category。 So by the way， you have K categories plus one。 right， That's the free space。

So the other K categories are occupied points that we see， and they have different colors。

So the accounting model will。Somewhat help with the averaging。

 because if you have contradicting labels。We're just gonna accumulate。

 And based on the frequency of observation， it will get。The probability that it's occurring the must。

Is there like， I know you described how its just like there's hallway and then Carinal direction in the center？

But is there any sort of like？诶， notion。How to set and define those categories。Question is。

 is there a rule？A guideline that we defined a number of categories。

I brought a secret book of categories here。I left it at home。So to finish this lecture。

I have to tell you that there is no rule for categorization of the scene。Because。

No matter what I choose， you can increase it or reduce it。So， it is。Again， it is。

 it is an open question。How to do it。 In reality， there are we have infinite categories。

Well it's hard to work with that， because。That makes it very challenging to come up with simple algorithms。

But also， we are limited。In practice， with the number of categories that we can actually detect。So。

Take this trade off that at any point， what's the progress。

 How many categories we can actually detect， whether that's the object， scene segmentation。

 deep learning。Gemetric method for segmentation of the floor ceiling， whatever it is， right。

 Put all of that together。Maybe you get 30。 Maybe you get1 hundred0。500， something like that， right？

Now， does it make sense for the robot to categorize 500 labels。A lot of time it doesn't。

 Maybe it does depend on the application。 So based on application， you can engineering that， right。

 So I guess that comes down to your intuition as engineer that you designed though。situationu where。

はい。It's just important to essentially create categories go and say like for to driving。😊，不 notで。

Is that the form of engineering Pro？That's the good point that whether in some applications like self driving cars。

We need some regulation that maybe well the minimum number of categories that your thriving car is built on。

 you must recognize people， other cars， bicycles， motorcycles。Traffic signs。Things like that。

 I think that makes sense， I don't think there is any ir regulation at this point。

But also our algorithms detect all of them。So， there isn't any。

Method that is not aiming to detect this many category， at least。So the semantic。

Segmentation of an image or a scene is a problem。In that sense， that how many categories we choose。

 Now， the way I got a resolution for myself is that question was haunting me as well。

To the point that。Is this the right direction？Because there's a specific question that I'm not able to answer。

The way I could。Okay given answer to it is that。This categorization。

Is human understanding of the scene。If I want a robot to understand the scene the way I do。

I can categorize it and label it for the robot。Then， it makes sense。Again， any number of categories。

 But even if I choose 10， that's a minimal set of my understanding of the scene that I'm transferring to the robot。

 So that's somewhat。

![](img/cd54da0d254f7f71c758101845203162_7.png)

Is a little more。

![](img/cd54da0d254f7f71c758101845203162_9.png)

Satisfying。We are transferring our。

![](img/cd54da0d254f7f71c758101845203162_11.png)

Seecene understanding part， seen understanding knowledge to the robot。Does that make sense。

AndAnother way to。

![](img/cd54da0d254f7f71c758101845203162_13.png)

![](img/cd54da0d254f7f71c758101845203162_14.png)

I fixed this。法 matter。Can't remember。 You have to move on。So continuous mapping。 So that。

 whatever we talked about was still discrete。 We're counting labels。Staff questions。So。

What they kind of do， this is maybe a little specific。

Or is the top right of the constructed map is a very thin line deck。

Indicates that there was kind of a scan that maybe got through。

 I don't know if it's around like on the X axis yeah exactly。So this seems to me that it。



![](img/cd54da0d254f7f71c758101845203162_16.png)

At least looking at this as a person， this might be some sort of sensor error and the pure reason why I say this is because in the general vicinity of this sensor output。

 there is no other reading。With that same type distance。

 but when we go to the map that shows us the variance word。



![](img/cd54da0d254f7f71c758101845203162_18.png)

The confidence in the measurement that's made， it has the same associated variance。

 it's nearly zero as the other ones。Well， bright， because even though this could be a glass， right？



![](img/cd54da0d254f7f71c758101845203162_20.png)

Laser beam is going through the glass。Or any transparent object。And behind the glass。

 maybe there is a wall。So the robot does not understand that。

 and that's a valid range measurement and anything along that beam is modeled as free。Which。Has。

Low variance， because it was free。And that's that's。It's a problem， right。

 But it's not a problem of the algorithm。 It's a problem of。Higher level， lack of understanding。

Because the algorithm is just consuming data that you give it and it will doing the correct job。

But it's not intelligent enough to understand that while there' is a glass and that's outside of this region。

 I only want to build a consistent area of this region。

And there is no connectivity between that what I see outside of the glass and this inner area。

And maybe I point out in the end to scene graphs。 We have a slide on that。 So that brings us more。

 brings us more to the current challenges in robotics。

 that there is a need for higher level seen understanding。

It is not enough to just go around and build metric maps。So we need。More than that。

 this is a good example of that。So I would say the algorithm is doing its job。



![](img/cd54da0d254f7f71c758101845203162_22.png)

This is not designed to solve that problem。And it will limit。

The scene understanding capability of the robot。So， we fixed the problem of。What did we fix。

Have have to go all the way to the back to the beginning。

Gres were assumed to be statistically independent。 Did we solve this？We did。

Please elaborate how we did that。We didn't。We're still discounting measurements in one grid。

 This is another way of。Inferring the map， we did solve this uncertainty problem。So 1，2，3。

Next idea will fix one and3。If we make the map continues。Meaning it considers correlation。

 local correlation for inference， but also it gives you a continuous model so you can query it will fix the first and the third one。

Could we say the fact that we have this seman。はいてつります。The way that we're kind of classifying each。

Could that be some sort of dependence across？そせね。The categorization are not dependent。

 We treat each measurement as。And a statistically independent measurement。

The measurements that we use are conditionally independent。Given current map。

So we are treating them as independent observations。

That's what we do in localization and that's what we will do in Islam as well。Now。

It is true that these beams that we have on a lidar， they might be correlated because after all。

 they are just observing maybe the same wall。There are some research to how to build a better model that correlates your measurements for a laser scanner or LiDar。

To give you a better model。It is possible to do that。 It will make it much more complicated if， if。

 you won't get anything nice like this。This is extremely simple to implement。If you have。

 if you need to run a Gaussian process or the neural network， to just capture that correlation。

This close form Beijing influence is lost。But there are papers on that， that idea。So the idea。

 it turnss out to make the map continues。 We can go。Several directions。One early idea。

That I worked on it for a while as well。 was to use Gahian processes。Now， lookgasian processes。

Are dealing with。Gaausian priors and Gaussian posteriors。 They're not。

Limited to Gaussian likelihoods。 You can。 these models can handle different likelihoods。

 If you want to know more about it， this is a great book。 Theres software。And。

That's what I read to learn machine learning。For the first time， I started reading this book。

 It's very clear。And I highly recommend it。So Gaussian processes are not scalable。

 That's the problem。 Now， what is the Gaussian process。 So whenever you assume your。

Poerio parameters here， map。All the voxels。A jointly。Distributed， according to a gas in distribution。

So， if。Your variables。Follows a finer dimension of Gaussian distribution。 Joly。 That's。

 by definition， is a Gaussian process。And there are ways to model and run inference or good libraries for that。

 This falls into the class of kernelnel methods in mission learning。That was the。

Previous big thing before deep learning。But there's cubic complexity because we need to invert the matrix of the size of the training data。

If you have hundred0000 points and you want to update the map， or if you have。10000 points。

We're not going to be able to。Inver the 10，000 by 10，000 matrix。Plus， that's an overkill。

 because probably。The correlation that we want is locally。It is nice to have some global correlation。

 but。Locally， will。Take us a long way already。Based on what we have right now。

So the next idea that is an approximation to the Gaussian processes。Is。Done in this work。

And it's called。Baesian generalized cannal inference。Now， they implicate， it is。

 It's a work that for exponential families of distribution， it will drive a model that。

We'll bring in a kernelel， and that kernel will show up in that categorical model。

And then when we run the same calculations。The result is that。To update。The posterior hyperparameter。

 We just need to wait。Each measurement by its correlation with its neighbor。Using this kernel。

 the kernel。That you can model up to you。And the default can be this Gaussian kernel。

 or radial basis function kernel。It's a Gaussian shape。Bell curve。That。We can model the correlation。

Between the current v cell， and then。Points around it。

So the consequence of that and the kernel is something that it takes two points。

 It validates that Gaussian kernel。 and it gives you one number between 0 and 1。

 So it's adjusting weight to each measurement。So now instead of。

Associating that measurement with the voxel that it falls in。

 we can use that measurement to update a neighborhood based on。Where the lidar point is。

 where the voxel center is。 and that distance is captured inside this。Radial basis function。

So the the closer they are， you get the full。Version of the measurement is close to one。

 If you're very far， maybe you get 10% of it。And that brings some form of continuity。

 statistical correlation。That is locally now is's in the model in in the。Model that we use。Now。

 another consequence of of this is that。Mave。X is， let's say， if one of them is your。The location。

3 the location of the Liar point。There isn't any limitation where to query。

 You can query any point in this space。To know， it's。This standss to that observation。

So that makes the map continues。 Now， the underlying model is not tied to a discretized。

Representation， although we might choose to work with those vs still， because it's convenient。

But in principle， this asterisk means that we can query any point。

Any point in the space that you want to know the effect of this measurement。We can query that。

And as usual， you can， as before you can get the mean and variance。 So this simple idea。

Will help us to make the map continues。Now I'm giving you the consequence of。

Using the result in this paper。But， the results are。Easy to interpret。 It's just the kernelel with。

Neighborhood waiting。So now we are talking about continuous counting sensor model using that。

Clonnalized form。Now you can go back and compare this carelized map。It's not widely different。

 but it does give you a smoother map。Some of the edges are smoother。If you have。

Contradicting measurements this。Carel has tends to have spatial smoothing effect。

 So over your map coordinates， it will enforce some sort of smoothness。

And you are able to increase the resolution if you want to at any time。

The library that I will tell I'll give you， I don't think it has zoom and enhance。

 Maybe you can add that option。Using this model。You can do the same thing with the semantic version of that。

And。Similarly， we willll have the smoothing effect。Now， this is your homework， right。

 So your homework is to。Implement these four figures that I'm showing you， the counting model with。

Just a discrete version of count model， the semantic version， then a continuous version for。

Which is a simple extension of。The original accounting model。So their homework。

That we give you next for mapping。 Home 6 is about。

Using this data set and replicating figures that you see here。Once you implement the2D version， then。

I trust you that you're ready to use the open source library in 3D。That's your extra credit。

 So you have to。Run that open source on a data set， and。Prove it to me。Now， one question is that。

Where the hell we get the semantic labels。It's not like the sensor is giving it to us。

RightSo going back to that question that if it's our construct。Makes it very difficult too。

Use physics to measure that。That's not going to be something that we can measure it physically。

So that's a problem。 But luckily， we， we're going to rely on some advances in computer vision。

 If we we use 2D images， for example， if it's a stereo camera。

Maybe you do image segmentation on the left image and then you get your point cloud。And， you know。

 already。The pixel coordinates for each point。And then you read that from the segmented image。

 If it RGBD is' even nicer because there's one to one correspondences between points in 3D and pixels。

Under the image。Now， every month， there's a better network， right， So this area is super active。

 I'm just giving you some examples。Every year， every month。WeWe have better networks。

 better results in this area。There's also a nice。

![](img/cd54da0d254f7f71c758101845203162_24.png)

Data set that。It's called semantic Kitty。So the key data set was for self driving cars。

When some people did the job。Of labeling all the lidar points in this data set。

So now you have ground truth and point clouds with nice semantic labels。

And there's a competition having the network that can label point clouds in 3D。

 So this is different from 2D image segmentation because we have to label lightar point clouds。

Directly in3y。There's no color information。So necessarily this is a supervised task。

So it's a supervised learning problem。Because if you make it supervised or unsupervised。

 then there's that question of。How many labels and what they mean。So it's hard to rectify that。



![](img/cd54da0d254f7f71c758101845203162_26.png)

So some of you， I believe， will use this data set in your projects。



![](img/cd54da0d254f7f71c758101845203162_28.png)

So we can use 3D segmentation and 3D segmentation。You can think about all of these algorithms that advances in 2D3D computer vision as。

Better way of getting measurements for your mapping algorithm。So each segmented point cloud is。

A snapshot， a scan of the semantic map that we want to construct。Obviously。

 if the labels are noisy as。They will be if you training a network and want to deploy it。

Then a single frame。The decision making， based on what you get from a prediction of a neural network might be unreliable。

 whereas this way of multi frame accumulation of the labels in this counting model。Will make them。

Seecene segmentation more reliable。Because now we look at the window of time and the frequency of labels that we observe。

And if there is any outline or false positive or mistake， hopefully it will get rectified。

 So the performance should be better。Always theoretically， because。

 and it is using data because we're just accumulating。More data。

So this has this notion of single frame and multi frame。Mapping。



![](img/cd54da0d254f7f71c758101845203162_30.png)

![](img/cd54da0d254f7f71c758101845203162_31.png)

We're going to watch some videos。 I always wanted to show videos instead of teaching。

Here is our chance。Maybe next lecture， I show you a movie。Instead of optimization。And hopefully。

 that will improve my。Raiing。If telle you， Ga Newton and league group， then you will hate me。

But three years after that， you really mail me。 I get emails later。It's too late。

I missed that race already。So we， all these ideas we。Worked on it from 2017 to2020。So about 2020。

 we could。We're on this experiment on campus。That's Cassie Blue。Made by agility robotics。

So in Professor Gr's lab， they work on control so they could walk a robot。

 we were collaborating on adding the perception to the robot。是的。

Person burst behind the robot is just for safety。 The robot is walking autonomously。

It's tasked using a simple planner to go around the sidewalk。The way the robot knows the sidewalk。

Is using this map。So this is around the wayfield， you could see。

The image that what robot sees is super blurry and shaky。

The segmented image using a neural network is very noisy because we had to label a small data set on campus ourselves。

There isn't any。Label data。And you will be amazed at the trajectory that you see。

 it is only that reckoning using an imvariant EkeF。It's not the s。

Where the tracking is good there's a high drift。But the top view is very consistent。

So the high drift is caused by some factors， one is the contact point that we assume in the model。

In reality， the robot is not。 It doesn't have foot point。 It's a line。

 so it can have some differences。 The kinematic calibration might be imperfect。

There are some sources of errors。We started learning that in the first lecture， I talked about it。

Helps with some of the high drift when we bring in learning for this assist estimation problem。



![](img/cd54da0d254f7f71c758101845203162_33.png)

So于。do with both camera。

![](img/cd54da0d254f7f71c758101845203162_35.png)

So here we use。The image from the camera to。Perform。Semantic segmentation。

Then we project lighter points to the camera。 We had to solve the calibration problem to know the relative rigid body pose between。

😊，The camera and the lidar。Then we use that extrinsic transformation to map points to the camera frame。

 Then we use the camera projection model to map the ber point。To the image。

 And then we read the label on the image。Then we end up with 3D labeled point cloud from Lier。

And that's how we built this map。You， we could use the RGBD camera as well。

 but that's not very good for outdoor。We've done that。It won't be as good as lighter， of course。

It's work done。lineDid you need to go online we're mapping online here， right figure out what。

So the map runs at two hertz， roughly。Not entirely real time。 The lidar comes at 10 Hz。

The robot needs to make decisions， so it is online。But if we have recorded data。

 you can easily run it offline。あの水や。Right， right。That's a problem， right， good question。 So good。

 good comment。Because the field of view of the camera is limited。

 The image is not seeing everything that the lighter is seeing。So what happens。

Is that all the points that are outside of the field of view get discarded。

Or you don't get a label for them。 You can use the point in the map， but。We don't get labels。

So there are practical challenges。个是你标的。Can we apply labels later， how。

 how much later we need to make a decision。We can only wait so much until the robots en grass instead of sidewalk。

It depends how fast you're moving。 if this was a car。The speed can be much higher。This is。

 this is relatively slow。So two heads wasn't too bad。So for the continuous semantic mapping。

 you can go to。

![](img/cd54da0d254f7f71c758101845203162_37.png)

This library。This is on。Dr。 Lu Gs kit， she was my Ph student。She graduated。

So there are some images and you can run this。Using ross and。Different data sets like Kitdie。



![](img/cd54da0d254f7f71c758101845203162_39.png)

Now there's an occupancy version of that that we built on this second library。

The occupancy version was done。 We used that， and we converted it to the semantic version。We also。

 we have also extended this to。

![](img/cd54da0d254f7f71c758101845203162_41.png)

Dynamic， now， we're not covering dynamic mapping， but。



![](img/cd54da0d254f7f71c758101845203162_43.png)

We talked about this that now， if。A car is moving。Here。And the map is aesthetic。

 it assumes the board is aesthetic。It's gonna leave long traces in the map。

And it becomes overconfi until you reobserve it enough to。Balanced measurements。So in this work。

 we added a。Prediction part to this map updating using labels。

 And the way it works is that there's a simple。Autoregressive process model that takes the scene flow。

3D flow。 So it knows where objects are moving。 It uses a norm of the flow to。😊，Mostly。

 down weight the labels。So it will try to prevent the map from becoming overconfident。

And as a consequence of that， now we can roughly track these objects。And the traces are gone。

So accuracy wise。 Now， this was， was a challenge to how evaluate dynamic maps because。Accuracy wise。

 it's similar。But if you look at precision， the precision is so much higher。

Because all the free areas are。Moodeelled now correctly。

But it's hard in a lot of data set to evaluate it because a lot of data sets are built for static maps。

 If you just concatenate all the frames using the groundous trajectory， you do see the trace。

 So the data makes it difficult to evaluate the true performance of a dynamic map。 So we've done it。

A new work that builds the data set。And also makes this using deep learning as a local mapping。

It's not public yet when it becomes public， I will share that with you maybe within a month or so。

For this sort of effort we。O with flow information do you also need？It's like ego motion or the road。

Transformmission of robust well to be able to information。 We do， because the scene flow。

Includes egomotion。We need to compensate that。 So what's left are the objects。

That are moving in the sensor frame。Yeah， the visual flow or the 3D flow of data。

Includes egg emotion as well。And by that， I mean if the environment is aesthetic static and we're moving as if the buildings are moving with the opposite speed。

Whereas the buildings are static， so we need to compensate that to get zero flow for the scene。

So now this is a very simple idea， but it shows that is possible the consequence of that is that we get higher precision and we can see the objects are moving as they do。



![](img/cd54da0d254f7f71c758101845203162_45.png)

It is a simple extension of。This first libr。So that's for the algorithms that we want to cover。

 There's a lot to think about and read in this area this is。A very attractive area。

 because maps are usually nice to visualize and easy to communicate about them。

 because we can show people。 They have a lot of applications， as well。😊。

This' is a very old paper by Professor Kpers， is in Michigan。

And I don't think he was in Michigan at the time。 In1982。

 he has a paper called the Ma in the Head metaphor。

It's about different literatures and different ideas about the cognitive map and how we。

Pceive the spatial areas， and。Maybe the topological understanding of the scene。

Maybe this is a good read， if you' like to。Read about a concept。 It's not about an algorithm。

 This is。A concept paper that talks about。Different ideas。

He has another paper that is more recent by。His group。2009， so。Somewhat old。

 but is still very relevant。Then they talk about this hybrid spatial semantic hierarchy。

 This is also interesting to read because semantics are not just in categorization。

 That's a very narrow。😊，Way of generalizing the math from occupancy to semantics。

There this notion of。Tropological understanding of the scene。Just being able for a metric map。

 realizing a graphical construction of the scene to know these are rooms。 This is a building。

 This is a highway。 Maybe this is a cafe。How can we do that， objects。

So this notion of semantics can be so much richer， and this hierarchy in this paper is talking about different ways of thinking about it。

So again， it's an interesting paper to read。But also。

 I should point out that in a lot of robotics literature， the semantic is。

Used and refer to these objects and categorization。 So that what they're really pointing out。

 they're pointing out to。Tools that we have， and we can use。It's less about concept。

 whereas in artificial intelligence literature， maybe they are more concerned about the way of understanding the semantics and how we define it。

So a very general way of talking about semantics is the idea of affordance。

Affordance means the utility of perception。So if I see an object， I can assign a value to it。

 and that will be the utility of that object for me。 And the reason you're looking at me now。

 you're not looking behind yourself because I am talking and I'm drawing your attention and all your affordance is gone to this area。

So this notion is very important for object manipulation。

 grasping and generally interacting with environment and people。

So this is a generalized notion of semantics。Affordance， which means the utility of。Perception。

Something more recent。From。Professor Car Lo's grew at MIT。This 3D scene graph is very nice， because。

😊，They modernized some of the ideas in the literature， and they added more。You know。

 features and knowledge and with a good presentation。

To have a modernized way of visualizing and understanding the scene。Now。

 the proposal here is that to have five layers。The first layer is this metric semantic map that we talk about。

 So what we talked about is really this first layer of。Reconstructing the floor or scene。

The representation can be mesh， can be voxels。 That's not。It's important， but that's not necessary。

 It's necessary to commit to that for。Talking about this idea。

The layer 2 is about objects and agents， the layer 3。That they introduce。

It's about places and structures。Layer 4 is about rooms。 Layer 5 is the building。So that。

Can give way of building this map。 Now， this is， at this point， is offline。

I think it's undergoing some work to be online， to be a real time way of mapping。

 It will be interesting to。

![](img/cd54da0d254f7f71c758101845203162_47.png)

![](img/cd54da0d254f7f71c758101845203162_48.png)

Havelf something like that。This is not the end of it， this is the beginning of it。

We're still trying to。See how we can build this sort of map using the robot and how the robot can use it。

 act based on it。

![](img/cd54da0d254f7f71c758101845203162_50.png)

![](img/cd54da0d254f7f71c758101845203162_51.png)

It's an ongoing。Research。In the robotics community。So the simulator has also people。

 people walking around。

![](img/cd54da0d254f7f71c758101845203162_53.png)

Because its simulation， you can have access to labels。 It makes it easier to。Maybe solve a slam。



![](img/cd54da0d254f7f71c758101845203162_55.png)

And right of a rehab？We have a plan to have a guest lecture by Tony， the first author of this paper。

IfIf everything goes well， we will have a guest lecture and I think he's going to talk about this work or his research around this area。



![](img/cd54da0d254f7f71c758101845203162_57.png)

So， stay tuned。Okay， so。What's this。Later at home。There is a paper as well。

 I encourage you to look at the paper。These are some reading and references that。You can take a look。

They're in the papers because they're new。They're not in the textbook。

The occupancy mapping is in the probabilistic robotics book， but the rest are in the literature。

You can read it from the papers。So that's the end of the robotics mapping。Lectture。

Have a great break。next time we'll talk about optimization。Or watch a movie。

