# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p17 -17-Lecture 17-RKHS Registration.zh_en -BV1UfAmeUE3e_p17-

So welcome to the second lecture on point cloud registration。In today's lecture， we will cover。

A somewhat new framework for sensor registration， but mostly in the context of point cloud。

Registration that we're interested in。I call it RKHS registration and it stands for Reproducing Carel Hilbert' Space。

It comes from the kernel methods in machine learning。I don't expect you to know what it is。

And I'm not going to teach you what it is by the end of this lecture。

 But you will see what are the things we can do with it and how to use it。If you're curious。

 then I will point you to more readings。So this is a framework that。We。Actually。

 using the lab and do research。So in the previous lectures。

 I talked about some of the published work and established methods in the literature。Today is。

Not so much for。I would say educational purpose， but to give you an exposure。

 what is going on in the lab， what are the topics that you might see coming along more and more in the next。

 maybe five years or 10 years。With different flavors， them， flavors of the problem。

 So this is generally a context of functional。Registration。

Functional in the sense that instead of working with data points that we directly measure as at discrete timer steps。

We lift data into a continuous space and a space that。

Some sort of function is describing data as a whole。 And then we can。

Work with manipulating terms in the functional space to find the transformation that explains the relationship between two sets of data the best。

This is not the only way to go about it， but it is a very general。Framework。

And you can have many realization and variation of this framework that I talk about it。

So the concept that。We're going to cover。 I'm going to rely on。

Previous lectures that we learned the concept of manifold。And league groups。But we will also review。

 and you see。Specific examples over it， again。But generally。

 the space that we work on its a manifold。 So the data points。Live on that manifold。

 An example of that is。The familiar are。3D space， where。

This manifold could be our familiar Art 3 when we had our point cloud in the previous lecture。

 So generally， we have a function defined on that manifold and points are samples。From。That function。

So for example， we have the fifth。Point cloud here。 And then we have the second point cloud。

When cloud Z。These two point clouds need not to have the same number of points。No。

 we need to have the measurements of the same place in the space。

It is generally the case that imagine you have a beam。A single beam that moves in the environment。

 and you sense。From the geometry。What is the reason we need to believe that as I move。

I will sense exactly the same point in the environment so that I can find a relative transformation at two different time steps。

😊，That's not guaranteed。 And， in fact， this often is's not true because of the。

Variable density of the point cloud。 The point cloud。

 as we move the sensor such as lighter or camera， is at best at discretized。😊。

Sensing of the geometry。As we observe。So that is a fact。

But also the number of points in practice are not the same。

 so there can be a lot of points that are not valid based on different conditions in practice。

 so the general setup is that we do not get the same number of points in ICP what we were doing。

 we were solving an association problem。To make sure we have the same number of points to be associated。

 then we would go ahead and calculate the residual and then solve an optimization problem。

In this framework。We will formulate the problem such that it is correspondence free。

 It doesn't need association。Whereas association is built into the problem formulation。

 So instead of iterating over association and solving the problem， we solve the problem one time。

 the association is a byproduct of solving the problem。

 and that leads to two narrative in the literature。

Should we solve the correspondences and then solve the problem。Or should we solve the problem。

 And the correspondences are the byproduct of solving the problem。The mainstream thought is that。

We should。Which has been around for more than 30 years。 We should solve four correspondences。

Extracting features， solve the association， and then formulate the problem and solve the problem。

And a lot of。Different challenges associated with solving the association， robustness issues。

 and so on。Another narrative that I personally subscribe to it。 This is from my research。

 And I think that's。A natural direction to follow， not not to replace the other narrative， whereas。

To cover an unexplored territory and see later， what is the more general framework that covers both of them is that we should solve the problem first。

 The association will come out of it for free。Now， within this framework。

 this is very aligned with another middle point in literature， which。

Is similar to the expectation maximization framework that I pointed out in the previous literature where the association are soft association。

 many to many association within the framework。 And that is why at the end， we know the association。

 because we can see which ones are。Highly correlated。 or they have the highest amount of。

Wed in the sense of thatt product so we could easily pick them to be the correspondences。

So this framework。In that sense， it is。Somewhat many too many association。

 but it is built into the framework， and we do not need to run near neighbor for search。

Although in the code， we might do it， but in the formulation， you don't see it。

That's a matter of data structure and implementation。

So the goal is to find a transformation that when we apply to this function。It results in。

Through the matched part for the overlapping part， there is a non overlapping part that we do not know。

 So the framework is able to handle unknown correspondences。Variable number of points。

 partial overlap。 And as we will see， it works on different setup for different manifolds and league groups。

 but also， it gives you an integrated model for incorporating color and semantic labels， unlike。

Previous matters that。Are not so natural to integrate。Semantics and geometry。

 this model comes with a natural integration of both metals。So some background。

As we talked about it before， for us， smooth manifold is any shape。That doesn't have sharp edges。

It's a surface。And locally， when we look at it， it just looks like Euclidean space。

 It's a flatter space， in other words。😊，Not bothering you with the formal definition of the manifold。

 There are local patches。 If you chop it， you can flat it， flatten it that part。 and that you。

 and you can define local。Charts， coordinate charts。And。Basically。Treated as Euclidean space。

And the chopping is in a way that， at the boundaries， there are some overlaps。

 and these local coordinates are compatible。 We're not gonna to face any issues If you change the way we want to parametermeize。

 For example， Ouler angles， you have many。Options， Z， Y， Z， X， Y， Z。

You're not gonna to have problem switching with different choices。

That's just a different way of dealing with local patches of the manifold。

The examples of manifold are a typical Euclidean space， R N。Any too sphere。Is a manifold。

 it's a two dimensional manifold。Taurus is a manifold。 Torus is built by。Two circles。

So circle is shown by S1， Taus is。Cortesian product of two circles。 in general， Tori is。

Cartesian product of。And independent circles。So imagine you grab this smaller circle here。

And then move it all the way around the other circle that will create a surface， and that's torus。

So another preliminary that we need is。The concept of in a product space。

The inner product is the generalization of that product。A vector space， V。

It can be equipped with an inner product structure。

Such that the properties of that inner product are that is symmetric。

 That means the inner product of X， Y equals Y， X。An example of it， again， is that product。

 of course。Satifies this。 It is biline in both arguments。

 If you multiply an argument with a coefficient， you can just bring it out of the。In our product。

If you have x plus Z。Again， because of linearity， you get inner product of x by plus。Z times Z Y。Now。

 if that。In a product of x with itself is calculated。 It's always greater than 0， unless x is 0。😊。

In fact， every inner product。Space induces a norm。Which is defined using that inner product。

So the enormous space spaces are more。Maybe general version of inner product of spaces。

 but every product of space is also a normed space。So the concept is。

 although we want to work with the inner product of functions。The concepts are the same。

 If the inner product of two vectors or functions。Is0。 That means they are orthogonal。

They do not have。A common direction in this space， they're not pointing in any common direction。

The higher the value of this inner product or thatt product means they're more parallel。

To the point that if the vector is the same， that's the maximum value is exactly parallel。

But of course， depends on the magnitude of the vectorismal。

So we will see how we use this concept to formulate the problem。

So examples of what things we can do with this framework before。

Making you exhausted with some equations。So， we can solve。RGBD registration。

What does it mean we have two point clouds， target point cloud based on the same term analogy we use。

Last time we have the target point cloud X， and then we have the source point cloud。

 each point cloud。It consists of a set of 3D points， as well as color information， color。

You could think about it as three vector， RGB， HSB， whatever。Color of space you like to work with。

So we have a three vector of color and a three vector of。Position for each point。

 the collection of them will give you the set X。As the target point lot and the collection of the other set will give you Z as。

Some sort of labeled point cloud， because every point comes with the label and that label is the color。

It could be other properties。Another question is， what is the transformation。

 original rigid body transformation in this case。As part of， this is the same thing as S E3。

That aligns these two clouds the best。This is the same problem as last time。 It's not different。

But unlike ICP， again， we want to work with a framework that。

Works with the variable number of points。Takes into account that the point clouds can have variable densities。

 Theyre not even when the associations are。Perfect in the sense of nearest neighbor。

They do not need to be the exactly same measurement of the same place in reality。

 And that's the problem。 The best association is not even the true answer。

So that is a fundamental limitation in the previous approach。

So let's say we have a kote camera we go around and we can just track using frame to frame accumulation of this registration。

Here is a comparison that with respect to the ground truth here on tomb data。We can track very well。

 Traracking is almost。Matching the ground truth。The baseline is。

A very successful method called direct visualtry。In some sense。

 it's similar to this method because directly consumes RGBD data without feature extraction。

 it is from a family of direct methods。But it's solving the problem using at least the square formulation。

Which relies on some。Notion of association。In the next lecture， I will teach you。

The derives of DVO and how we can register RGBD using lease scores。

 This is still very valuable method in practice。But what we talk about today includes that。

 You can reduce this method to leave you。Another example on the left side， I have two circles。

 So the previous example， the manifold was R 3。In this example。

 and the league group we were using for registration was S E 3。 In this example， the manifold is。

Circle。What is the legal of that is aligning this red set and black set on the circle。S， O2。Right。

So it's the circle group。So the legal group is acting needs to be the symmetry group of the basis space。

 It leaves the circle unchanged， but it moves the point clouds on data space。In the same way。

 the rigid body transformation is a symmetry group of R3。So the are points at the solution。

 as you can see， they're not perfectly aligned。 So the method is not trying to match points。

It's looking at the entire set points as a function and how they're best aligned overall。

And that's a much better notion of alignment， as opposed to trying too hard to。

To reduce the distance of certain correspondences to 0。That will not serve our purpose。Well here。Now。

 this is， obviously。A toy problem。 But what is the real world example of this circle registration。

Does it look like a clock？How about clock synchronization。Imagine I have to。Processses to computers。

 I can measure time。And each of the computers。And I know the clock frequency。

And each digital computer。I press some button and record a sequence of time， right？

And with some delay， I press。B on the record time。 I know there are there's an overlapping part。

 where there's a beginning and ending that they might not。OverLap now。

I want to find a delay between these two。Systems。If I know the frequency， I can map it。

 map the time to phase。 And then my problem is registration on the circle。

 So I should be able to perform clock synchronization。

Only if I know the clock frequency of each computer。Now， it seems very doable。 I haven't done that。

 It should be easy to test on two Linux machine just recording time。

The same sense that you can work with Torari， many circles it might。

In my work on a network of basically clocks。Its possiblessible， I have not done it。

Feel free to try it。Sounds like a fun problem。Now， if you have。Tauus， imagine the basic space now is。

Tos， I have a particular shape of a star here。Now， remember， the points live on the manifold。

 The points live on the torus。You cannot move these points in the outside world in the。

Ambmbient environment， right， points live on this shape manifold。 They do not live in our two。

 So we are only allowed to move these shapes on the surface until they are matched。

So we can handle that， then you can see here they are aligned again。

They're not aligned in the sense that。Points are perfectly matched。Where the shapes are match。

And the name of these methodss correctly from old time in literature is shape registration because the goal is not point registration。

The goal the goal is recovering the shapes， registering two shapes。A more interesting example。

 Imagine I have。Images of a planet， which we can get from satellite imagery。I want to。

Register these images to reconstruct。Maybe certain maps。

The colors could be height or some other properties。So in this example。

 we're getting the map of earth and。Then。So this is。The first one is。Some contour map on earth。

We perturbrate。So the manifold is。Basically， the circle。Right。

The circle is not the same as two independent。 The sphere is not the same same thing as Torus。 right。

 This is as 2。So the interface of this bald earth is。The planet。That we're doing registration on。

 Then we perturbrate using whatm。In 3D， the circle becomes。Spphere。

 so we have to rotate this using S O 3。So our transformation here， we can only rotate。

 Translation doesn't have any。Particular meaning here。We perturbebrate， And then in the third one。

 what's happening。They are aligned correctly， right。You have example codes， you can look into it。

But we were able to solve this problem。As a toy example。In this application。

 what would you do about the fact？それて。What do we do about the fact that。

Earth is not the perfect sphere。So we have that free for rotation。嗯。

Its often modeled as a little story。Now this is a to example， right。

 but let's say in practice we're dealing with that challenge， we're actually working on a project。

 we have to solve it。One option is to ignore if it， if it gives you good answer。 The other option is。

Now， the problem is， if the manifold is。Als。As I will itemize the problem formulation。

 there is an inner product。That that can define the carvaature of the space if it's an ese。

The carvature of the space will vary， It not uniform， like sphere。

So that inner product will help you to calculate the gradient。That guides you along the eps。

So it gets more technical， but。If we are solving it using an optimization and we're using the gradient。

 the gradient is responsible for。Following the flow correctly on that。Manifold surface。

The more complicated the shape， the metric that we need to define the gradient will be a little more complicated。

So we still we as long as it's a smooth manifold， we can solve it。 That's not a problem。But。

 of course， we have not。 I'm not talking about real problems， right， These are toy examples。

 conceptual。Hopefully we will see some。Future results in these areas。Another example。

 what's the space here？The league group is Se2， the manifold is R2， right？Right。

 we can rotate and translate now。So we have two smiley shapes。To faces。Initially， they were separate。

 and then we register them by finding an S2 transformation。Again。

 they don't have the same number of points。 You see that there are areas that。

It's actually only blue。But overall， the shapes are matched correctly。Now。

 what you see in figure  one and 2。At the solution， we calculated the hessian。

The second derivative valve。The cost function， the objective function with respect to the transformation。

In this case， the Hessian， which。If we're working with a twist in our tree， right？

Or you could say twist is an S E2。Haum will be a matrix that maps the vector from R tree to。R 3。

 this will give us a  three by three matrix。Not fun to calculate， but possible to calculate by hand。

So that will give you。An operator， a matrix that maps vectors from R 3 to R 3。

 Then take the eigenvalues of the this operator， the weakest eigenvalue as a vector field。😊。

Which what we do， you take the lambmbda 1。And then put it in the， because， remember。

 the eigenvalue of the Hessian is some vector like twist。 Then put it in a basis of the Lee algebra。

Then generate a bunch of points in R 2。As homogeneous coordinates。

And then apply this vector field to all of these points。

 It will generate this vector field for you that you see all these vectors are moving around。

So the vector field related to the weakest eigenvalue is describing the symmetry of the shape。

 The the most symmetric way is if you rotate about the central axis。They were learning。

 we were learning about the symmetry。From geometry， the second order derivativeveted。

The strongest vector field。Consponding to the strongest eigenvalue describes the。

Direction that you will。Probably break the symmetry the most。 If you move along this vector field。

 you create the biggest amount of difference。三。Interesting and not so explored observation。

So that was all motivation。Should we continue。Or it's enough。If you're not solved。

 we shouldn't continue。You can just practice driving some Jacobuvians instead。😊，Un legal。

Anybody interested that。All right。So we all agreed that problem formulation is more fun than driving the Jacobviians。

So the general framework， we want to keep it general because when we see a problem。

 we create an instance of this framework， and then we apply it。

That gives us a framework to organize our thought and solve a range of problems instead of just formulating a single problem。

We define。This continuous sensor registration framework。 It's as as follows。

 It's non parametric because we will construct our functions using data。 We will not。

Create a parametric model。Such as lines or polynomials or planes。

We will not work with any particular shape， but we can model any shape in the same sense when we solve the linear regression problem with Gaussian basis。

 we could regress any function。But we never specified， what's the order of the polynomial。

This is doing something similar to that。So the sensor registration problem is defined as a five tuple。

First thing we need is a league group。Similar to the examples we。Discussed。

Then we need a smooth manifold。Then we need the action of the league group。

Smooth action of the legal group and the manifold。It needs to be a deioomorphism。

 It needs to be differentiable。Which is the groups act smoothly。

 Usually it's not a problem when you rotate and translate。That is satisfied， usually。

So in the same sense that when we rotate points on a circle， we can act on it。 that's what it means。

Then we need an inner product in the Lee algebra。 We're not going explore it much。

 but this is a technicality because we need to derive the derive the gradient。 If we want to use。

 for example， gradient。Acent or decent to solve the problem， we need to drive the gradient。

This metric describes。The structure of that manifold。However。

 because we are solving for the transformation， it needs to be defined in the Lee algebra。Why did we。

Why didn't we define an inner product in。The previous lecture， we just。Linearized。

Using first order approximation of the exponential map。 And then we drive with Jacobkuya。

 we never talked about。A metric。So that's the weird thing that we can do。

 We can drive gradient and Jacobn。As in a metric free sense and league groups using a matrix exponential。

That's。Somewhat nice because you don't need to think about a metric。A more general version of that。

 that。A is also doable on league groups is。How we calculate the gradient in Rimanian geometry。

 For that， you need a metric because the differential of a function。Along a vector x is。The gradient。

 is the inner product or dot product of the gradient， width。Some direction， vector。

The differential does not need a metric to find。That's a delta of the function。

Mathematically speaking， the gradient needs this metric。 You need a metric to tell you。

What is the magnitude derivative of their function along that direction that gives you that differential。

Based on how you choose this metric。It can change the gradient， right？And typically。

 it's chosen in a way that describes the geometry of the space you work on it。Whi simplest way is。

What is it， It's the dot product that we use， right？When you do tailor expansion。

 we use the dot product。This is a generalization of that。So the last thing we need for the。

This five people is a kernel。 A kernel is a symmetric， positive， definite function。😊。

Such as that Gaussian kernel。We'll see why。This is for the geometry。 then we need。

Free items for the information space so we can encode something like color or semantic labels。

The information in space itself is a three tuple， such that it has。And inner product is space。

For example， color， the color that we see， like say C1， C 2， right， they have。R。GB vectors。

 And then you can define a dot product or inner product of。C1 and C2。

So the space of all three vectors as colors and their dot product will give you this inner product space。

But we keep our option。 We want to keep our options open。 doesn't have to be color。Any。

 any label that you want， Maybe you learn features using deep learning， and you want to use that。

 That's also possible。So we keep our options open。 We we're not limited to the dimension of the label。

 It can be 1000。You can potentiallyly scale that product， right， It doesn't have to be。

Just the plain dot product is up to definition。Now， on top of that， each set of points。Come with。

Labels。What it mean， what it means is that。There is one to one correspondences between。

Points in geometric sense， and their associated labels。

Which is interesting enough that RGBD cameras are giving us that every point is coming with an RGB。

There is a sensor that physically is satisfying these conditions。This makes it very interesting。

So what he's saying is that we need a dense set of labels。 Each point should come with a label。

 and this L is describing that。Now， once we have these。We can use。

G1 to G5 generally to build a gradient that will allow us to solve the problem in the sense of geometry。

I 1，2， I 3。 It allows us to encode。The information in the point cloud。Now。

 without telling you what is an AHS， unless somebody asks。You， that kernel。

 if it's positive definite， a positive definite kernel is a kernel such that。😊。

When you evaluate this， it's a generalization of positive， definite matrices。ItCurrent。

 it' positive definite when you value this is positive。Now， if your kernelel is gaussing kernel。

Some left to scale。Of course， it's always positive。The coefficients。

 they don't have to be positive in general， but let's say if they are positive。Well。

 it's always satisfied。Colorors are always positive， right。

 that product of two color vectors will be always positive。So generally， this is。Satisfied。

 but the can must be。Technically speaking， positive definite。 And， of course， it's symmetric。

 It doesn't matter if we valid。K of X， I， X， J or K of X， J， X I。Now， given a positive。

 definite kernel。We can define a vector space of function called reproducing can hberter space。

So we define our inner product spaces。Hilber spaces are。Inner product spaces that are complete。

So any inner product is space， including our end with that product。

Is a hillil ofter space if it's complete， completeness means that it contains all its limit points。

Every cache sequence that you define will convert， in that sense。The space is complete。

 Nothing weird will happen。 When you take the derivative， we calculate the limit。

It includes all its limit points。You can always complete a vector space to make it a complete inner product space。

 So these are matter of technicalities， but。That's the structure we need。

So a reproducingkenal heater space is a more special type of fieldberter space。😊。

Where you have a kernel such as this that acts as。Evaluation， functional。

Because the vector space of function is not a space that you can。Point evaluate functions。

It's very abstract。 You have a vector space。 Its elements。 instead of vectors are function。

 We do not know how to。Evaluate those functions necessarily。There is a structure in。

If I show it like this， R KS that allows you to。Evalate your function at a particular point by taking its inner product with a kernelnel。

A familiar example of evaluation functional is a deelta function。Right。

 the integral of Delta function with any。Functionable。

Result in the point evaluation of your function。F x， Delta X。

Minus a D of x that will give you F of a。So Delta is evaluation functional。And， in fact。

 is a very special case of this RHS。 You could choose your kernel to be Delta。

It's just not as interesting， because。It is just a point whereas this Gaussian car really covers a neighborhood。

We can talk about correlation in a neighborhood as opposed to just a single point。

So this kernel is a more general version of that the delta function。 In that sense。

 It allows you to evaluate your function。Together， that is called R KH S。

 The entire kernel methods in machine learning is built on this space。Well， not all of them。

 because some of them， they do not need the kernel to be positive definite。 For example。

 a support vector machine。And a lot of methods and kernel machines are built in this space。

 Gaussian processes。They're operating in this space。So， an interesting result is that。

It was proved first around in 70s and 80s， later in。90s， again， with the simpler proof that。

If you try to minimize。Any cost function that is also regularized。In search of。

A function that describes your data the best。Not to feed a function。

 search over all class of function that describes your data the best in this space。

 What you will find。😊，This is proof。 This is a theorem that your function always will be。

In this form。It surveyed some of。Some coefficient coefficient。Times。They care no。

Every kernel is centered around one data point。 If you have n data points。

The best function that you can find that minimizes the regularized cost admits this representation。

 So this is very powerful because we know that we need to work with functions that。😊。

They have this structure weighted some of some coefficient times the kernel。

And we're going to build on this result to。Former functions。

So the goal is to give me a giant point cloud。 and I will turn that point cloud into a single function。

 one object that describes every point on that surface。If you will。

Is this representation still not very？It is nonpometric because。WeDo not describe any shape。

So I'm misconcernstruing the fact that theres a kernel that exists。

 I'm misconcernstruing that as a circle。审提审。Well， that alpha is a parameter that if you build your model such that。

That you're supposed to find that alpha， then could， you could call it parametric。For example。

 in Gaussian processes that's nonprometric， you can still write it that way。

But it's not so much we're after Al， because。Alpha just has a formula based on the kernelnel itself。

So both of them are possible， but generally this is called nonpometric representation of the function。

Because it has as many tens as your data points。There are more data points you collect that n， right。

 This sum will grow。In theory。The the hilber of spaces。

 the inner product of functions are infinite dimensional vector spaces。However。

 as a result of this theorem。那。Nes a lecture on its own。Is that。

We can work with a subset of the space。That is only spanned by data points。

 yet we can represent the function。This is very magical because now we can solve problems using the data that we receive as opposed to dealing with infinite sum。

😊，These are all wisdoms before deep learning。Then I'll point out how it's connected to deep learning。

Alright， let's now turn the point cloud into functions。Without pain。

 you can forget everything I said， just do this。Per carel， Gaussian Carel， for example。

Your function will be weighted some of these labels times kernel。 now the labels are vector。

That's okay。You can keep the labels as vectors。And the kernels are centered around。Each point。

Remember， the labels L sub x of X I means the color of that point， for example， right。It's。

It varies based on the point， but it does not vary based on the transformation。

 It's fixed as you rotate or translate。I also noticed that we're not normalizing。

 So because we're not gonna query functions。 We don't need to normalize if you wanted to actually。

 because it's a function query， the new value in between to interpolate。

 then theres a need to normalize in the sense of kernel density estimation。 So to make sure。

We're not adding all the neighbors to get a bigger value。

 It's not necessary to normalize because we're not going to query the functions。

What's the meaning behind this notation for？Blue box where you've got one dot。Well。

 the dot is the variable。Because X I is a 3D point that we received in the point cloud。The other one。

 we should write a variable， anything。 Let's， let's write。 Maybe we could write less's say Z。

Or we could call the basis Z and keep it X。If you like to write F of x。

Or maybe y is better because I'm using Z for the second cloud。So y can be any point。 Now。

 it's a function。 you can evaluate it at any point。So we do the same thing for the Z cloud。 Now。

 we turn the entire point cloud into a single object。😊，With as many points as we want。Now。

 one reason we need。This structure of inner product is space， because。

We need a reason to talk about alignment。 alignmentignment geometrically is tied to。

The angle and how parallel are two vectors， these vectors can be functions。

And the inner product or dot product is a natural tool for that。

 That's why we need the inner product space。So we define the inner product of the two of our functions to be like this。

 This follows from that R KHS。Space， it comes with this definition of the inner product。

So the inner product is such that。We take the dot product of labels That will give you some。Scalar。

 let's call it C， I J。 And remember， this is a double sum over I and J。

And the kernelel evaluated that。The basis of two functions， X， I and Z， J。 Now。

 it is a double sum because for every X I， we should loop over every Z， J。Okay。

 if you have 2000 points in the first cloud and you have another 3000 points in the second cloud。

 the total sum will be。2000 times。3000， which is。6 million terms， right， It's insane。

So we lifted the problem into function space。 Tyically， this happens。The problem。

Basically blows up and it becomes super large scale。Is that any better。No。You're giving up too fast。

At first， look， it's not。 And that's。That's what the。

Reviewer of the paper we wrote first thought because we didn't mention explicitly。

It was somewhere in the paper， but。It wasn't explicit。This would not be attractive computationally。

 However， this is a sparse double sum because this kernelnel。

It's only valid in a neighborhood small neighborhood。

 There are only so many points in the second cloud that falls into the bandwidth。

 this shape of every kernelnal term。So， you end up with。Some local。Terms in this double psalm。Which。

 if you evaluate。This as a matrix， it's in a。 I have it in a figure。 I forgot to include it。

This will be。The dimension of this matrix， right， This matrix will be sparse。 You get some of the。

 you know。Hms are non zeros。 Most of them are 0。Besides， we can control that。

 you can make this kernel using its bandwidth to be very sharp。 then it will become a sparse。

If you want to include more point， you can increase the bandwidth。So it's is trade off。 generally。

 more bandwidth is good because you correlate more points in a neighborhood。 But， of course。

 it's going to make it slower。So。It seems to be quadratic。But because it is spae， it's somewhat。

Like linear time。Roughly。So it's pretty good in practice， you can calculate it。

And the latest library we have， we do this in GPU。So it's very fast。So we're ready。

 we have a metric that measures the alignment of two functions。

Let's maximize the dot product or inner product of these two functions。

When a transformation such as age is aligning them。

How this transformation acts on a function we do not know yet。

 but it is possible to talk about it like this。So the goal is to maximize the inner product。

By searching over a transformation that is an elite group。Such that these two functions are aligned。

 if they're aligned。The angle between them is minimize。So the angle between between two function。

It's similar to how you write the angle between two vectors。Now。

 if the transformation is an isometry， that means it does not。Change the scale。

It's not going to scale， right， It's a rigid transformation。What happens？

If the transformation is an isometry， it will。Not change the norm because it does not change the norm。

Then， basically。This denominator。Right， well be independent of age， the transformation。

So we are actually minimizing the angle between two functions。Or maximizing its cosine。Same thing。

But because the transformation is a rigid transformation。In this case， we can only。

 We can just go after maximizing the inner product。 However， if we work with。

 let's say Sim  three group。You you need to go back to this formulation。

 that's because now we're scaling as well。So， we have。So we successfully constructed problem。

 all the stories that now we have a problem。 If we can solve this， we get the transformation。

At this point， it doesn't matter。What it looks like or what the space is living on is just it's just an objective function with some decision variable。

So the objective function， F of H。Is this。Some constant C I J， these are do products of。Every color。

And the X cloud with every other color in the J cloud。However， if the kernelel gives you0。

 then you don't need that in the sum。Another magical thing is that。

The transformation that acts on the function that we do not know what it is。It induces。

The same transformation。Inverse of the same transformation。And the input。

This is very important because otherwise， we have to work with this operator。

This transformation that acts on a function is an example of an operator。

 If these functions are generalization of vectors， you can think about the operator as a generalization of。

A matrix。 matrixtri is a finite dimensional operator。What are the examples of？

Infinite dimensional operators。Different gradient。That knble operator integral。For example。

 I define an operator to be。The second derivative。With respect to time。Plus， some。Constant。

Positive constant。That's it。I'm going to talk about the position function of a particle。

That is moving along some X axis。The differential operator acting on x。Will give me。

Its equation of motion。If it's not forced。This is the second order differential equation for mechanical system you define。

It comes from this differential operator， similar where you can define integral operators。But anyway。

 we don't want to go that way。 It seems too hot。 We're not trained for that。If you are。

 give me a call。We decided not to go that way。So luckily。

 from representation of theory of legal groups， we have this result。

That if every legal group can act on。Typically， roughly speaking on any vector space of any dimension。

However， this result holds now to see。This why in a very， very naive and simple way， imagine。

I have this line。Y equals F of x。And I'm going to write。I'm going apply the transformation to。

The outside， and I'm going to write y plus1 equals f of x， right？

I'm just applying a translation as the transformation。Which is， of course。This is x， just a line。

Same as y equals x minus1。Now， both of them doesn't matter if it's 5 plus one equals。

X or y equals x -1， and x equals1。It crosses the line。 and you get this。locket。We get this line。 Now。

 this is a very simple example， but shows this concept of linearity。

When it's applied to the output of the function。It induces the inverse of that transformation in the input space。

This result is the same on stioot。 It's like league group on。Reectctorspace of functions。

Comes from a very advanced topic。We do not need to。Be worried about it。 But this enables us to write。

They invest the transformation here。Which is nice。 Now I can just go ahead and solve it。

 This is just like ICP now。It's just wrapped around the kernelel。Which we did that as well。

 We had that robust kernel。There isn't anything different here。Than a typical optimization problem。

So we are in good shape to actually solve it。So let's make it more specific。 Let's talk about。R 3。

 so things make sense。My kernelel will be this Gaussian kernelel。Some distance you could call this。

 this is called signal variance， but some positive coefficiention。Exponential of some distance of X。

 Y。Divided by some length to scale。Maybe we could choose a different。Notation as well。

 that L is not related to these labels。The Euclidean distance is a typical choice。

 but you're welcome to。Change the assistance if you want to or your problem。For example， in ICP。

 we had point to point， point to plane。In GICP， we had that probabilistic distance。

 which is in somewhat plain to plane。And other types of distances。So the color dot product。

 it will just give you。Something like R 1， R 2 plus。G1， G2 plus B1， B2。RGb。

 product that you read from images。In practice， we actually found it to be more useful to work with。

😊，It's just three color map， but that's just a side point。You get marginal performance improvement。

 HSV， a panel is better。That was an advice from my colleague who works in computer vision。 He said。

 change to change it to HSV。 We'll get better results。And it did work。So。Maybe it helps you as well。

 If you have RGB change it to HS3， maybe it makes your results better。So the goal is to maximize。

This function。To find the rigid body transformation。If I know the gradient。

 I can just do gradient descent by following that direction that will give me an OD。

The SD state solution of this O will be will be。At this city state， h dot is0。

 that's the necessary condition from calculus。So the necessary condition is that the gradient must be 0。

And if I have the gradient， I can do gradient descent like。

H K plus 1 equals H K plus alpha times gradient。Right。

Which we talked about before the continuous time version of that is this ODE。If you don't remember。

We can。Rightrite it like this on the left hand side as alpha goes to 0 is， in fact， H dot。

So oil air integration is just one way of doing it。

 which we will not do oil air integration because it's a league group parameter。

We cannot add add the delta term。So because we're maximizing， we're doing gradient ascent， of course。

 we could multiply a negative sign， and then you would do gradient descent。This is。

Let's say the the simplest solver that we can build。 And that's what we're using here。 You could do。

We probably， but that's the simplest。Sover， because we only need。

A first order derivative information。 And we talked about it， that because these。

Contours of the function。 These level sets are。Constant the function does not change。

The dot product of。The gradient。Any。Delta movement along that curve will be。

Z if the gradient is not zero， the only explanation is that the gradient is orthogonal to level sets of the function。

 so it's the maximum direction of the maximum acent towards the peak here。

So we're going to do gradientationcent。There several pages deriving the gradient。

 I'm going to spare you。Nobody has the patience to listen to that。

So we're going to ask some friends they good at math。 this is the gradient。And it is the gradient。

 if your kernelel is Gaussian and。You're working with this。S it tree transformation and R 3， right。

 So you could within this setup， you can change a lot of things。 And it's still the gradient is。

 is the same。 So that's。Pretty cool。This is my twist。This is the gradient。Add the identity。

But you know that。When I。Move。An a group。We learned that。The differential equations。

 because like this， because we have to transform。The tangent vector to the Lee algebra。Right。

 these ares actually like this。And the way you can see that is。Let's say H is T is the translation。

 We have R T 0，1。So I have R T 0，1。Times。Omega and V。So what happens， We only need to。Rotate。

Which will give us the general。The differential equation， the reconstruction equation for S3。Right。

But we can write it for rotation and translation separately。So， moving from。

Moving in the manifold from one point to another point， it just needs a rotation。

When you look inside。In general， you could just write it like this and ignore it。If you look inside。

 we're just rotating the vectors。 it makes sense because translation will not change。Where we are。

 it's not that。 It's not going to change。Magnitude of the velocity。

 But what direction we move it will change。The magnitude of the velocity。 that's what we see here。

So we know the gradient， and this is nothing but the reconstruction equation of league group。

I should actually use。Sllledge。Which is exactly what we use here。So we compute the flow。

 Now we need to integrate。We talked about these endless times that never add them because it's an element of the group。

Just like you did in your homework， you have to integrate。If。Simple integration。That is。

 in fact the exact is using the exponential map。We could introduce some。Step size。

Because you might not want to take the full step with a gradient。Usually， it's a very bad idea。

An optimization。Especially for gradient as or descent。So ultimately。

 the exponential term will give you a deelta rotation and deelta translation， whatever that is。

The gradient along some direction， with some subide， It tells you that do a deelta rotation。

 do a deelta translation， multiply them。Using matrices。

 that results into the integration rule that we need。So rotation is accumulated by multiplication。

 The translation is the previous translation plus。Rotated version of Delta T。

That is compatible with S E 3。Group。That we deal with。That's it。 So we formulated the problem。

 We solved。The problem using one instance of solvers。Does it work？We did all the work。

 The question is， does it work。Of course， it does。 I wouldn't waste your time。 I would never do that。

To my beloved students。

![](img/207b13e755e14669d8d2c7c535926153_1.png)

Let's see what race says。T it talks on this video。 a new framework for registering semantic pointhouse。

 This is an extension of the work。 Now we're going to bring in the semantics。



![](img/207b13e755e14669d8d2c7c535926153_3.png)

Rch sensors， like streo。嗯。Have you found in many。

![](img/207b13e755e14669d8d2c7c535926153_5.png)

no。Good back。I'm going to introduce semantic CBO。

![](img/207b13e755e14669d8d2c7c535926153_7.png)

A new framework for registering semantic coin cuts from0 and RGBT cameras。

Branch sensors like satellite on RBT cameras。Can be found in many modern autonomous robots。

The have used in localization and mapping algorithms could generate the pulses at different times stepss。



![](img/207b13e755e14669d8d2c7c535926153_9.png)

These French sensors can provide rich information not only the geometric measurements but also the color information as well。

 The main question is how do we combine the semantic that' how you watch my lectures unified that works。

Especially， we are interested in the point cloud registration problem。

 which is a building block of many 3D computer mission and slam systems。

My job is to distract you from what actually learning from this video by talking。



![](img/207b13e755e14669d8d2c7c535926153_11.png)

That it is a hard problem because the observations could be pretty noisy。

 The two point might just partially overlap。 The scene is tless。

 There might be different densities of the observations。

 and there might be some dynamic objects in the scene。😊。

Existing methods usually formulates the problem as some optimization problem。

Different methods might have different representations of the plain cards。

 and then the cost functions are defined accordingly。

Itter you closest points is a very famous coin car registration problem。

It relies on one to one data corresponds and represent the point code as a discrete set of points。

The cost function is minimizing the pairwise geometric residues。

It is possible to incorporate extra color or intensity information by adding the regulars for these colors。

EMICP differs from other traditional ICP index that It covered this last time as a hidden miracle and then use EM algorithm to infer it to the middle。

However， premiseizing the correspondence could take a lot of time。

Normal distribution transform is another class of quickker registration methods that works very well in practice In trade it represented bankout as a v subvaion distributions。

And the cost function is basically the maximum likelihood。

 fitting the observations of the second point cloud into the distribution of the first point count。

 However， efficient and accurate disization is challenging。



![](img/207b13e755e14669d8d2c7c535926153_13.png)

In this group， we propose a new point registration method that is continuous。

That has doesn't rely on one to one data correspond。

 and it is easily extendable to non geometric informations like color or ses。

Let's go back to our basic problem。 One， we want to find a good translation for the2 X C Z。

 and we want to define a suitable cost function for them。Finally。

 we wanted to be get association free。TheThe two point called representation should include both the geometric and color semantic observations。

Here's example from the Kity dataset set。 let's pick a single point X from the ste observation。

This X has the color。I color of a pixel。Which is basically a three dimensional vector。

You also have a corresponding semantic observation from some neural network。

 and it has a different dimension and the color。We combine them with the tensor product。

And this is what we call the hierarchical setic presentation for a single point x。

 or we can call it as a label。So this label will encode the non geometric informations for a single points。

Besides the hierarchical setic information。We also include the geo information with a square as exponential kernel。

This kernel would have larger values for points that are close and has very very small value for points that are far away。

So we do this for all the points and we obtain a function representation for the entire point called FX。

It is essentially a weighted sum of geometric kernels， while the weights are the labels。

Now that we have the continuous function representation for the point class。

 we want to define the cost for it。 We want the cost to avoid the explicit hard data association。

The cost function should measure the alignment between the two points。

For vectorors in the inner product space， we can use the angle between them as a measure of alignment。

 and this also applies to point color functions。So here we define the cost function as the inner product of the two functions of the point code。

The nice thing about this caused function is that it avoids explicit hard data association。

And we actually aligning the two functions instead of two pairs of points。

After some mass manipulation， we will arrive at the doublemetric double sum of geometric kernels。

 where the weights of the geometric kernels are the visual features。

 So this objective function will contain the information from both the geometric and nongemetric information。

We want to perform the the we want to perform the great as to maximize this objective function。

A nice fire product of this cost function is， similar to the traditional normal vectors。

 you can use the coosant angle between these two functions to measure the alignments of these two point。

thegeneNot the complexityveity of this function angles when it's represented against normal angle and this here in the have larger values。

So to sum up。We will propose a framework for registering hierarchical semantic point calls。

 The point calls are represented as continuous functions that takes the geometric and nongemetric information into consideration situation。

And the per problem is formulated by maximizing the two functions。



![](img/207b13e755e14669d8d2c7c535926153_15.png)

In our practical implementation。The computation for the double sum might be costly。

 so we done sample the points with open CV fast point detector selector。



![](img/207b13e755e14669d8d2c7c535926153_17.png)

Also， we compute dish elements in the double sound in GP in parallel。In order to speed things up。

Here are our experimental results。We we evaluate on both an outdoor and indoor data set。

 It is an outdoor data set that provides color serial cameras。It has multiple sequences。

 with ground truth。An arrow was evaluated by translation and rotational drip per 100 to200 until 800 m。



![](img/207b13e755e14669d8d2c7c535926153_19.png)

The K st point clouds are computed via EB loss， as so you can see the picture on the right。

 it provides a st point cloud， but there are still noise from the color and geometric。



![](img/207b13e755e14669d8d2c7c535926153_21.png)

And also， we get the semantic observations from the neural network。

 but still there are some noise visible。

![](img/207b13e755e14669d8d2c7c535926153_23.png)

Here is an example of aligning two point。the first one is in orange， and the second one is in blue。



![](img/207b13e755e14669d8d2c7c535926153_25.png)

Here's another example in the in the KT data， sequence3。



![](img/207b13e755e14669d8d2c7c535926153_27.png)

And in this example， we， we want to in this example， we want to align the entire sequence。

 frame to frame。And the curve in the middle in green is the accumulating trajectory from our frame to frame registration。

The point cardss are stacked together based on the transformation from our algorithm。This is not s。

 It's just accumulation of frame to frame registration。 It will drift。



![](img/207b13e755e14669d8d2c7c535926153_29.png)

This is a close a close look at the stacked point cloud。 Still。

 the green trajectory is in the middle。And we can see that the cars， the roads are pretty clear。



![](img/207b13e755e14669d8d2c7c535926153_31.png)

This is the quality comparison between the proposed methods and several baselines。

The ground truth is the black dashed curve。 The three solid curves are the proposed methods。

 and the dot dashed curve are the baselines。This is another sequence with a similar comparisons。

 Still， the the black dash curve is the ground truth。The solid curves are the proposed methods。

 and the dot dash curve are the baselines。This picture shows that the proposed methods have lower drift at both at lower and higher speeds。

 while some baseline may have higher drift when the speed goes fast。So this is a positive result。

 when using both color and se information， the proposed method will have a lowest。

 translational and rotational drift。T UM data set is an indoor data set that use RGBD cameras。

 This sequence be challenge because it includes some non structure， nonte environment。

 and observations could be pretty blurry。

![](img/207b13e755e14669d8d2c7c535926153_33.png)

Here's the example in a structure but non thing。Still。

 the our trajectory from frame to frame registration is highlighted in green。

 and then we set the point out based on the our registration result， as you can see in the map。

 the point the thing is pretty featureless and can be challenging for traditional registration methods。



![](img/207b13e755e14669d8d2c7c535926153_35.png)

In the quantitative result， we can show that our geometric results are comparable or better than geometric based。

 and our color results are comparable or even better than the color baseline。So to sum up。

 we propose a no point registration methods that represent hierarchical point curves as continuous functions。

We introduce a new way to measure the alignment， and we demonstrate comparable or performance versus space size。

 The code is release open source。😊。

![](img/207b13e755e14669d8d2c7c535926153_37.png)

Any questions is welcome。You can talk to Ray if you have questions。



![](img/207b13e755e14669d8d2c7c535926153_39.png)

So Ray took the time and implemented this in GPU， there's a couda code。



![](img/207b13e755e14669d8d2c7c535926153_41.png)

Depends on how many points you use， but I think it works on。嗯。Inception。

Youre going to layer by layer inside。Mobile robotics。He implemented a GPU。

 I think something between 5 to 10 Hz we could run it。 it's real time。

 but it also depends how many points you use with2，3000 points。 it works。Well。

But also notice that the stereo point clouds and outdoor are extremely noisy。

 This results using that type of point cloud is very surprising。😊，Within the start of the lecture。

 you mentioned that this can be used to award for dynamic。也是在。

So do we need to segment it or does this handle。The question is。

 I mentioned we can handle dynamic objects， I did not mention that。And the beginning of the video。

 it mentioned that dynamic object can cause problem。

 but this framework is not explicitly dealing with that So that。

If the object is moving and it's super close to the camera， it can cause a serious problem because。

The moment it's gone， the point classes you see are so different that it becomes an outlier。

 that's a problem。So。Now， some open problems。So you could see that we extended using tensor products to include color。

 intensity， semantic labels from deep learnings， so if you learn features from deep learnings as long as they're not dependent on the transformation。

 transformation imvariant， you can easily use them as labels for your points。That's possible。

 And it's interesting。We used fast feature detector from open CV。 again。

 if you can replace that front end that tries to downsample and select key points using deep learning。

 that's very exciting because then we have key points， not necessarily high quality。

 like feature extraction。😊，But it somewhat it's the semi dance structure of the points we see so we can track。

That will be interesting as well。This is an example on tourists。 If we cut tourists and open it。

 then we can look at it as。R2， because Tos was two circles。

Cut it along that top top area and then open it， right， then look at it as an R 2。

 So this is between minus pi and pi。 And again， minus pi and pi。

we flatten it and then evaluate because this is 2D， we can evaluate and visualize the cost function。

 We are only solving for。Two angles。With the objective function itself， that's a 3D space。

 we can visualize It counter plot。Depending on what you choose for the length scale of the kernelnel。

In fact， we can make the problem convex。Here，0。5 makes the problem convex。 no matter where you start。

 you will find a globally optimal solution。Which is here， I think it's the same cloud。 So 0。

 the center is there。Point that will maximizes the inner product。However。

 if you reduce the length scale， it can make the problem very complicated。Many local maximum。



![](img/207b13e755e14669d8d2c7c535926153_43.png)

If I think you have a。

![](img/207b13e755e14669d8d2c7c535926153_45.png)

Visualization of this。So as we reduce L。It does make the problem nonconvict。

 then it matters where you start your search， especially if you're doing gradient。



![](img/207b13e755e14669d8d2c7c535926153_47.png)

Desent。So one。Our open problem is that if I can dynamically choose this lengther scale。

 the hyperparmeter， that at every stage of the optimization。

 it keeps it convex and gradually makes it more complicated as we get closer to the deepest。

Maximma mini or maxa here。Then。I can find a globally optimal solution。 However。

 it's extremely challenging to do that， so。What is the right objective function to handle that。

 That's the question。But if you choose the length scale large enough， usually it works well。

 but it takes more number iterations。对这对说是。The red dots are key。Red dots are。 These are different。

Local maxa。Theres a function in Matlab， it gives you all the local maximum of the surface。Now。

 a side note， you might wonder what's the relationship of this way of looking at the problem with existing works？

I'm going to show you that we can reduce this problem to the weight that least squares。So generally。

 the kernel uses some sort of distance metrics。 Let's say we work with the exponential kernel。

Define this bandwidth times the label， some sort some weights so that。

Inner product basically is the double sum of some weights times the exponential of negative of the distance squared。

 That's what we're dealing with。We're going make three assumptions that will reduce it to least squares if they have the same number of points。

 of course， in the least squares problem， That's the case。

And if they are ordered in such a way that they are associated。In this the original problem。

 we don't need that。 We don't care about the order of the points。

 If they have the same number of points and if they are ordered that we know the associations。

And if we。Basically。Ignore softft association and only evaluate this double sum for corresponding points between cloud X and Z。

 that will reduce the double sum to a single sum because we only need to loop over correspondences。

Then， the。Objective function because it becomes a single sum over some weight sum Ki the exponential of corresponding points。

this is eye eye， I drop the second eye。What's simplicity。

Now do a tailor expansion for the exponential。The first part is constant。 of course。

 it does not depend on the transformation。The maximization of exponential of negative of this distance becomes minimization of this weighted least squares problem。

 So the least square weighted least squares problem is a special case of what we're doing。😊，And。

 in fact， there is something called generalized list squares when you deal with。

This soft association。Not necessarily carnels， but you do evaluate many too many associations。

So this is important because we want to link it to other works。So you know where we stand。

 So we are generalizing what we see in the literature。How can we solve this？

If the ratess are constant。It's just the weight at least the squares。 If the weights will vary。

We can use， we learned， we can use IRLS， right？So now we can use second order solvers。

Because it's easier to solve。Some open source solvers。So the initial version of this。

 when I published a work is。Here， I do have a simple Matla class function。We can take a look。

 There is a C plus plus version of that as well， in this repository。

The GPU version where it incorporates semantic labels it is in this repository。And。

This is for the journal version when it has examples for sphere， circle， and some other。

Fonun examples。This is indirectly related to this work， Mink， one of my patients students。

 He used this idea to build a loss function to solve the problem of depth from a monocular camera。

Because of the continuity of the loss function， we can， as a result， we can。Get better results。

 but the message is that we can regress something like windows of a car。

 because generally other methods， even if they perform better， they miss transparent objects。

Because the， it's very difficult to。Get the depth value of a transparent object for the metric loss fails in that case。

So he's using that en3y to enforce this geometric。Consistency in a soft way。 And then as a result。

 we can regress Windows of the cars much better。 You can take a look。At his work。

 And there's a video， as well。If you're interested in this problem， you can。An exhaustive。

Version of the work is in this 50 pages of。Written work。The second one。

 which I recommend looking into that is what we saw the presentation of it， Ray。

 another Ph see in my lab。He's the developer of this board。

Thishich is probably what you might want to use in practice。 I this work， not all the other stories。

That we talked about。This is the work for depth from Monocular camera， the third one。Now。

 this is our recent attempt to use deep learning to solve。Corresponence free registration。

 It only works on S O3。 If you remember， I said when we have， we know the correspondences。

 we can solve point cloud registration in closed form using horns method。 and the way it works it。

It centralizes the point cloud， builds the cross correlation matrix， use the SVD。

 and then recovers the rotation matrix。What we're doing here。

 we're doing horns method in feature space。 The features we learn are equivariant。

 They have the same rotation as the initial as the input point cloud。 Therefore。

 in the feature space， because of max pool operations and some other operations in neural network。😊。

We recover the exact correspondences if it's a copy of the same object。

So we can apply horn's method in feature space。Which makes it somewhat better because in the inputus space。

 we don't know the correspondences。 Now， in the feature space， we know。How it's related to this work。

This could become。The front end or。Whatever you want to call it。

 but this can become the featured learner of this framework。

Whether you want to learn features for appearance as labeled or replace the points that are input of the kernelnel。

 because those points， so long as they have the same orientation translation of the input points。

 then you can apply this framework on top of the features learned from an cuvariant neural network。

 This is our current work。However， if we want to solve it for S E3， it needs to be S3 equivariia。

There are recent attempts。 There， There are approximation versions of the weekend。

Learn features that are S3 equivarian， but mathematically， it has a problem because。

There is no exact form for S3， because S3 is not。ToConfuse you more。

 There is no ad jointint imvariant in a product in this algebra。Okay， so。

This should give you a flavor of what we actually do in the lab when we go to work。

We don't work on ICP， but variants of ICP are useful in practice。A lot of teams in DARPpa challenged。

 Probably they used it。 They built good maps， but good engineering can make it work。

But this is somewhat the next generation of that。So that's it for today。

And next time we're going to talk about DVO， it's the point cloud。

It's a RGBD visual that uses least squares for solving the problem。



![](img/207b13e755e14669d8d2c7c535926153_49.png)