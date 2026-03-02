# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p15 -15-Lecture 15-Optimization & Smoothing II.zh_en -BV1UfAmeUE3e_p15-

![](img/e74251031d2f54abb5b4e1005ad07fd9_0.png)

Welcome to the second lecture on optimization and smoothing。 Today， we have three objectives。



![](img/e74251031d2f54abb5b4e1005ad07fd9_2.png)

Building on the nonlinear lease squares that we covered， we want to extend it to。

A class of problems that。They do not necessarily deal with the least squares problem。

 If the objective function is not in the form of least of squares。

We want to learn what to do with it， and that will lead to a new algorithm called called iteratively reweighted least squares I R L S。

The second topic is about robust estimation。The class of M estimation。

And the third topic is how to solve the optimization problem on manifold and in particular。

 on league groups。

![](img/e74251031d2f54abb5b4e1005ad07fd9_4.png)

![](img/e74251031d2f54abb5b4e1005ad07fd9_5.png)

So， let's review。The nonlinear leaves the squares problem。The objective function。

Comes in the form of the norm the square of a residual。 The residual was a map from the input R N to。

A vector R M。And the norm was the Euclidean norm。In this type of problem。

 the residual is not necessarily a linear or a fine function， so we had to linearize。

Knowing how to solve the linear is squares problem， the gaps new an algorithm。

Was telling us to linearize around the current gas at the current iteration。😊，Reconstruct。

And I find approximation of。The nonlinear residual around the current gas， initially around x 0。

Therefore， they fine approximation。Which is in the form of a X plus B。We'll have a constant。Part。

Resual is a function of x 0 plus a Jacobbian matrix evaluated at x 0 times at。Delta movement。

 we call it D here， or you could call it Delta X。 When we solve D。

 and then we integrate by adding it to the previous value， and then we continue until convergence。

So that's the idea behind。The gaus knew an algorithm and how to solve a non nonlinear least squares problem。



![](img/e74251031d2f54abb5b4e1005ad07fd9_7.png)

So we solve the linear problem many times， why。Iterating。

 So this is a very common theme and idea when the problem is not linear， linearize and iterate。

So the algorithm is。And the basic form is quite simple to implement。You write a loop。

You might set a fixed number of iterations because you don't want your solver to go。

And optimize it forever。And the convergence is when。Let's say， the norm of the Jacoban。

Transpose times R is 0。 that that's a good。Condition。Why， because。

The gradient of the objective function is。Jaubban transpose are。So if the norm the gradient is 0。B。

Half satisfied the necessary condition。 We can stop。 We are at the。Optimal point。

So this was the Gauss Newton algorithm。

![](img/e74251031d2f54abb5b4e1005ad07fd9_9.png)

One natural question that comes up is。What if the norm is not the Ecclidean norm。Because it。

 depending on the problem or what you're after， you might choose not to。

Deefine the objective function to use the Ecclidean norm。 And that's very common。

The Euclidean norm wass。One type of norm that is very common。We pointed out that you can call it。

L 2 norm。In general， you can have P norm。 We defined it last time that you raise each term to the power of P。

You add them up。Absolute value of each term， because if it's odd。

 you don't want to get negative value。 And then you take the。

You raise the sum to the power of one over p。That's the pen norm。

So we wish to minimize the objective function that is in the form of a P norm， not two norm。

And P norm embraces the power of P。2。Just minimize the sum that there will be equivalent of。

The same objective function。 There's no reason to。Again， raise it to the power of1 over P。

 So this is no longer the least the squares problem。 so we can't use Gauss neuro algorithm。

It's just the generic， nonlinear programming。 You could use nonlinear solvers。

 but it does not possess any interesting structure like Gaus Newton。 So in Gaus Newton， we。

Work with the Jacobuban， we drive at Delta。Instead of working with。The gradient。

 the advantage of working with the Jacobian was that it gave us the approximation of the Hessian。

 so we were benefiting from a second order like Sal。By only calculating the first order derivative。

 the Jacobian。Whereas if you choose to。Work with the first order derivative and use a nonlinear solver。

 We are not benefiting from a second order solver。 We are just using a first order solver。

It will take more iterations， as we。Showed you with some examples in Julia。

So the trick that historically。As far as I know， it was around around。Maybe 70s， 80s， 90s。

 it was very common 20 years ago to solve a lot of machine learning problems using this technique。

Is to。Convered。The P norm。To await at least the squares problem。And the way we do that。

By redefining the optimization。To be like this， define your penome to be a quadratic term。

Let is waited。Now， the way the list squares， if the weights are constant。

 it is as easy to solve as or as hard to solve as。The least a squares problem。 That's not a problem。

 You will just see a weight matrix。In the solution。As we saw it in the regression examples。However。

 the weights， the trick is that we don't want to change the objective function。

 The weights are defined as to to be the diagonally。

The absolute value of each residual raiseds the power of P -2。

 So when you calculate the right and side with the given weight。It is still evaluating the p norm。

We have not changed the optimization。How will we trick。The solve by。

Alternating between solving a least of squares problem and updating the weights。

 So at the time we solved the problem， we assume the weights are constant。

 So we solve a least of squares problem。 Then given the solution， we update the weights。

And the next time， the weights will change。 So the difference between a weight least the squares problem and。

IRLS is that the weights are not constant。Hence， the name iteratively reweighted least the squares。

Now， this is a trick to solve the problem。 It does not come with any guarantee or。

And in nice theoretical results， it is very practical。 It's a practical way of solving。In general。

Noor problem。In the context of robot bikes， what's an example where we use it to？L team。

Robust optimization。 That's the next example。 That's in the context of robotics。 we will use。

This to solve a robust estimation problem。So in practice。

 you could start from setting the weights to be the identity。

Solve the list squares problem that will give you an initial guess， then iterate until。Hopefully。

 converging to。The true solution。

![](img/e74251031d2f54abb5b4e1005ad07fd9_11.png)

Now， notice that even if the residual is。Linear。And the norm is not。L2 Nor。We still need to iterate。

So when it， when you initialize， the least the squares is， of course， exact。

 but we still iterate because we are minimizing a P norm， not。L 2 norm。 So I R L S will iterate。

 even if the residual is linear or a fine。Because the norm is P norm。



![](img/e74251031d2f54abb5b4e1005ad07fd9_13.png)

Example。

![](img/e74251031d2f54abb5b4e1005ad07fd9_15.png)

So we， we're going to go back to the same linear regression problem in this case。The data they have。

Is contaminated with outliers。 Outliers are data points that do。

 they do not agree with the underlying process。That shows the trend。So therefore。

 they can buy us the estimate。嗯。Substantially because by definition。

 they are not describing the trend and then a model that we fit to data can be completely wrong。

So dealing with outliers is very important in practice if they exist in data。

So the model is not changed。 We still have the same。And data points。X is a vector。

 T is the target value or output is the scalar。We use a linear model， linear in weights with。

The same Gaussian bases。We still use the first basis to be the bias term。 So we do not。

 we do not change any。Modeling part， however， will we change。



![](img/e74251031d2f54abb5b4e1005ad07fd9_17.png)

Is the objective function。The objective function， instead of being L 2， L 2 norm is now L1。

 L 1 norm is。Traditionally used for solving robust optimization problem。And the reason。For that is。

Because L2 is calculating。A Euclidean distance， and is trying to。

Somewhat interpolate between different length， distance between measurements。To come up with。

Some notion of average distance or。Shortest distance， with respect to。S of a squared of terms。

 whereas L1。Is working with absolute value and taking the。Straight lines。

It's just summing straight lines。 It looks like， it's called also Manhattan distance。

 If you look at New York， all the roads are straight and intersecting and orthoagonal。

It's type of a distance that it will sum that type of this roads for you。 You move。

Exclusively in one direction and then add another direction。

 It will not try to make a circle like a Euclidean distance。 In other words， if you draw at L2 norm。

That will define。So， a 2D ball。With norm， L 2 norm will be。So if the norm。Is less than some。Thisance。

 this will be a circle。Right。Because。We're talking about。R being x is squared plus y is squared。

However， if R is。Absolute value of x plus absolute value of Y。 This will be very different。

 Were basically talking about。Something like this。This is very different。 We are not。

Moving in a circle。We're moving along these lines。And that is why when you solve the list squares problem。

 we need to iterate， even if it's fine。So that's the idea behind L1。Norm， and because。

It's not trying to satisfy both direction。 At the same time， It tends to ignore outliers。In practice。

Another property of L1 is that it promotes。sparsity。

 when we regularize the norm of the weight with L1， it a lot of weights tend to go to 0。Again。

 historical reason for that is that we， when we want to promote sparsity。

 this is a topic in a sparse coding literature。We want to actually minimize。L norm0 norm， the0 norm。

It's discount counting the number of participating weights。

As opposed to what's the value of the weights。And you raise the power。Right， up 0。

The definition of zero norm is that if w1 exists， it's1， right， if W2 must be removed， then it's0。

 right。Now， however， this is not an easy problem to solve because then we're dealing with binary values。

 It's not a smooth。Because it's difficult to solve。 L 1 is a proxy for L 0 norm。 So a lot of times。

When you see they add L1 norm as a regularizer to promote the sparsity because it's a proxy for L0 norm。

So that's some historical and background。Idea of Y L normm is popping up here as a regularizer。

So the objective is when we assemble everything， minimize。The same problem is with L1 norm。



![](img/e74251031d2f54abb5b4e1005ad07fd9_19.png)

We defined a design matrix。

![](img/e74251031d2f54abb5b4e1005ad07fd9_21.png)

How to solve this。This is not least the squares。 however we convert the problem to a weighted。

Lesa squares problem。And we define two new weight matrices。Based on the instruction in IRLS。

The weight matrix must be the diagonal of the residuals raised to the power of P -2。P is one here。

 so the power becomes。Negative one。So that when you calculate this line。

 you get the original objective function。With that， we can differentiate。

 The gradient will be this term here。Calculate the necessary condition and the solution will be in this form。

没有。Only in one iteration， right。Once we find。The optimal W。Then， we have to。Reeval。

These weights for and make them ready for the next iteration。 So the next next iteration。

 when we evaluate the new W， this B and G will be different。😊，And that's how we iterate with win。



![](img/e74251031d2f54abb5b4e1005ad07fd9_23.png)

Weight and the decision variable。

![](img/e74251031d2f54abb5b4e1005ad07fd9_25.png)

However， you need to be careful because。

![](img/e74251031d2f54abb5b4e1005ad07fd9_27.png)

In the weight matrices， you can see that we have。

![](img/e74251031d2f54abb5b4e1005ad07fd9_29.png)

1 over ratess or one over the residual。 What if the residual is 0， you， we want to avoid。

Division by 0。 So in practice， when you。Implement。We usually use something like maximum of。

That positive number and a small number， right？ So when it's too small。Just use the Delta threshold。

 some some small value to make it numerically stable， otherwise。

You might face all sort of inconsistencies。So another name for L1 norm minimization is least absolute deviation regression。

It's robust to outliers。And one regular riseizer10 promotes a sparsity。

 There's no guarantee IRL S convers。So we tend to set a maximum number of iterations。

 and you need to check the solution to see if it's correct or not。



![](img/e74251031d2f54abb5b4e1005ad07fd9_31.png)

![](img/e74251031d2f54abb5b4e1005ad07fd9_32.png)

So if you look at the example， how in practice I converted these equations into an algorithm。

You can see it in this L1 linear regression example。As you can see， a lot of weights are zero。

So out of。15 weights。We are only using five weights。So one third of weights are non zeros。

Two third of weights are zeros。In some， it's nice because we are estimating the function using a small number of bases。

 And that's computationally attractive as you。😊，A scale this。Instead of having。50000 points。

 Maybe you can use 500 points and get a nice approximation of a surface。

 So it is very attractive computationally。😊，And what would you call these points？Outliers。

They are clearly not lying in this simple example， not lying on the true process。

 which is the blue curve。They are not describing this function。 They are outliers， but the solver is。

Ignoring them。Because of the choice of the norm。The way the solver behaves makes it robust。

 It ignores。These outliers to the choice of the distance or norm。

Can change the behavior of the solver substantially。And these are the survived。

 We call them survived basis， these。Circleled once。Now， there are other good ones as well。

But the optimizer is recognizing that they're not adding anything。We could。

You had equally good results by just using these five wayss。So automatically， they're being ignored。

 even though they are good data points。The generalization of this method in the context of。

Beijian inference， when you can get also uncertainty for regression， is called。

Relevance vector machine RVM。RVM is a method that you can do Bayesian regression and classification using these kernels。

Or nonlinear basis。And it is a sparse。It behaves similarly。And RVM is a degenerate model。

 compared to。Gauusian processes， but it is more scalable。

Is degenerate because it's not using the whole data points， and it usually picks a subset of them。

And it's not a equivalent of。Gp。But Gaussian processes are more general。

 and but theyre not as scalable。So RVM is parametric， assumes this linear model， G is non parametric。

Just some side notes。몸비 세가 돌。does with you。もし。So're using less weights or less bases。

Compared to something that may be more robust。でめたつけのあげす。 Kevinevin Murphy in his。

Legendary machine learning book， probabilistic machine learning book。Is summarizing this。

 If you're after speed， go for RVM。And the scalability， if you're after。Accuracy and performance。

And the problem size is small enough that you can afford more computation go after GP。

That's the bottom line， ignoring。All the technical。And papers， topics around these two models。

Is that a good summary？Yes。😊，question for the say it's not。彼子。We have an all。In this case。

 I added the outliers， but in reality。Outliers exist because your sensor， for example。

Gives you outlier the fact that the laser beams。Go through transparent objects that will give you an outlier。

There is a window， and you will hit the window as an obstacle。

 But the laser is telling you the obstacle， maybe it。10 m away。 you see the five， because。

Theres a wall behind the glass。 So that's an outlier。And there is no way we know it。If we could。

Detect outliers that， and it's possible sometimes。 And that's obviously nice。 And we get rid of them。

But it's just sometimes it's not possible。 We need。A better， smarter way to。

Not letting them to contaminate the。Good part of data and corrupt the solution。

Robust optimization is one common approach for that。 And this is an example of that。

There's a question in chat that does the fact that IRLS requires inspection make it useless for auto time of systems？

No， because you see endless papers， they're using IR L S。

 And a lot of time when the setup is nice and we carefully initialize。And implement。

 it tends to work well。However， again， the fact that it does not come with a guarantee。

That doesn't mean that we can implement something on a robot like this and assume that it will work out of the box all the time。

But a lot of time in practice， it does work。It's a tool that you want to use。

Based on the problem at hand。It's not。A generic。Guaranteed to work out of box methods。So。

 it's still useful。

![](img/e74251031d2f54abb5b4e1005ad07fd9_34.png)

So the next topic is。

![](img/e74251031d2f54abb5b4e1005ad07fd9_36.png)

M estimation。 And in the， at the end of it。Itll get tied back to I R L S。 That's how we solve it。

So the previous example was just an one example of M estimation L1 norm。There is a general class of。

Robust estimation method。And this is not the only one。 There are other methods as well。

One very common method in robotics is called M estimation。

 M stands for maximum likelihood type estimates。So the idea is that we wrap。

The residual around the kernelal。Or a norm， if you wish， to call it a norm。

Sometimes we call it kernel is ultimately a function， takes the residual and gives you。

Scalar a number。Then。This will be。Gene， the generalization of the maximum likelihood and the maximum likelihood。

Estimation。This。If L is the objective function and in the context of a statistical estimation is the likelihood function。

If you take the negative log of that， that's called maximum likelihood。

So that's a very special case of this method。And we will see this in Islam s when we define the likelihood when we see the observation。

We define the cost function to be。The likelihood。 And then we take the negative log of that because the noise we assume is gassian。

 The log will cancel the exponential。 What we're left with is。At least the squares problem。However。

 that might not be the best choice if we're dealing with outliers。So the general idea is that。Use。

A robust two outliers kernelnel， instead of L2 norm。Or you can definey it this way。

You can go back and define the necessary condition using this kernel。

 This is another way to define it。 Well， in general， we wrapped the residual around。

This new function。Obviously， it's assumed to be monotonically increasing and being nice to optimize。

 not making the problem to behave widely should be continuous。

Changing monotonically so we can optimize it efficiently。



![](img/e74251031d2f54abb5b4e1005ad07fd9_38.png)

So how does this change the problem？It turns that it's not that。Difficult， we。Write down。

The necessary condition， which。Says the Tctic gradient said it to be 0。

Take the derivative of the new objective function with respect to the decision variable。

 which is now wrapped around the residual and then again， wrapped around another function。

Use the chain rule。By chain rule， we know that。This will be the partial derivative up there。Ro。

 the robust。Carnel times the usual。Derrity above the residual。Set this to zero。We use a trick。

If you multiply and divide this by the residual。And。Deine this to be your new weight that depends。

 of course， on the residual。This will be an example of the weighted least squares。

 because if your problem is a weighted least squares problem。If you have。Some weight。Right。

 when you take the gradient， the gradient， of course， will be。The wait times。

The residual times the partial derivative of the residual with with to the decision variable。

 So what we see here。Is。The necessary condition for the weight that list a squares problem。

There is a problem。 The weights are not constant。 The weights depend on the residual。

 If we want to consider it as a complicated function。It won't be nice to solve。So what we do。

 we use IRLS to solve this， alternate between updatinging the weight and solving a least squares problem。

 and that's the easy way to bypass this difficulty。While we're benefiting from。

The robustness of this。Clonnal function row to outliers。In general。

 it's it's not difficult to see that。As we are doing it here， the weights。Have this definition。

So the weights are partial derivative derivative of the row function times one over residual。

 So it's very easy to。Include this in the library。 You pick the。Row function。

 The weights are already clear what they need to be。 It's just a derivative of。

The objective function times one over the residual。And of course， again。

 you don't want in practice to divide by zero。

![](img/e74251031d2f54abb5b4e1005ad07fd9_40.png)

When we have one over the residual。We need to be careful and mindful of that。



![](img/e74251031d2f54abb5b4e1005ad07fd9_42.png)

So the new problem of M estimation。Ends up being a weighted least squares problem。

 The weights are not constant， but we can use I R L S。Sol where to get a solution。

So this is a new class of problem。 It's a robust list square。 and we also learned a way to solve it。

 which is called IRLS。

![](img/e74251031d2f54abb5b4e1005ad07fd9_44.png)

![](img/e74251031d2f54abb5b4e1005ad07fd9_45.png)

Let's revisit the L1 norm example。 This is another way to formulate it。In this case。

 instead of L1 minimization。I wrap it around a last function， or robust kernelel。

You have several choices in libraries and literature。

 one very popular one in common one is called Kohi loss function。Koshi loss function has this form。

And。This is a scalar。 R is a scalar， right， So it takes R and alpha is just the hyper parametersameter。

 It's a parameter。 you can tune。Its derivative is calculated here， so the weights。

We know the weight are like this。 So as we iterate， we。Calculate the residual。

 and that will give us the new weight。So alpha is a parameter that controls when where the last function behaves。

Soly， nearly。If you plot this。You will see something like this。So the original least squares problem。

 right？It's a quadratic loss function。Outliers， by definition， they have a large residual。

 They do not agree with the model。So an outlier will have a very large residual。Now。

 there is a big difference if the outlinelier is here or now suddenly here。

It's quadraly increasing the distance。 What is the effect of this distance and the gradient。

You get a huge gradient that will dominate all the in layersars， in layersars。By definition。

 agree with your model。Right， so they don't understand any chance if the gradient of one outlier will dominate them like this。

It's a robust kernelnal， what we'll do for you。Is。To bend the size of this quadratic function。Now。

 there are many ideas。 You can truncate it。Maybe you start here。All sort of models， right。

 You can design。 You can design this function to be。Something that in general。

 you wanted to behave like this。 You want to bend this these two sides of the quadratic functions so that the outliers are being ignored。

They do not have。Possible that this is the region you want。 you consider it to be the end lier。

 right。And it's controlled by this hyperparameter alpha。Then after that。

 anything will be the same to you。I do not care if the residual has this value。

 this value or this value。They're all equally bad。 I want to ignore them。So in simple words。

 that's the idea behind M estimation。Does that make sense too。Everybody。

And this is not the simplified graph。 This is because the。This function row， is it？

Is taking a scalar， right， You can visualize it。 It looks like this。And the residual。

 although the decision variable can be high dimensional， the residual itself is a quadratic function。

Right， so。The red curve is our。Itsqui。What a norm of it， essentially。

So we solve the previous problem。 Of course， in this case， we are not promoting sparsity。

We're going to end up using。Whatever inli we have。But as you can see， the outliers are， again。

 are being ignored。However。The weights。Are all non zero。

 So that's a good way to compare with the L1 solution。 We are not aiming for a sparsity。

We're aiming just for robustness。You could， of course， add。

The regularizer to make it a sparse as well， if you wish。To have that。



![](img/e74251031d2f54abb5b4e1005ad07fd9_47.png)

So this wraps up the two topics that I want you to。

Learn around the optimization because you read them in papers， you see them as tools in libraries。

And you want to know， what does it mean to choose a robust kernel in G 2 O， for example， or in G TC。

 What does it mean。To tune， to change that hyperparameter of khi loss to be 2 to be 4。

 So you know that you're， you're choosing that region to be bigger and smaller。

 You have an intuition about it。And the examples I gave you are simple enough you can play with them and build more intuition around them。

So the next topic。Is。About extension of these ideas， the nonlinear is square problem， too。Lee groups。

What if the decision variable。Is an element of a league group。Which is always the case in。

Robotic has state estimation problem。 We want to estimate a pose。Pouse maybe in velocity。Rotation。

It's typicallypically， a matrix。Leg group element。So if it's not。

 we know how to do it by now if your state is， if you're solving over a bunch of points。

Or in general， if it's R N， if it's just position， maybe。We learned how to do it。

 that's the topic we covered so far。The problem is， I want to solve for。A rotation。

Or a rigid body transformation， or in general， any of the league groups that we discussed。

We have spent quite some time and learned about filtering。

Some got a little more involved because in optimization， we have more freedom because we iterate。

The solver tends to。Be more forgiving。For simplifications， whereas the filtering， you have one shot。

 you process data， you move forward in time。The more accurate your model is to integrate and move forward。

 the better results you get。 We will never go back in time to correct previous estimates。

So the filters are less forgiving， because。Because of。

The lack of looking back at data and reprocessing data。The performance of the invari E KF。

 as opposed to extend the common filter。Showed us a big difference。So luckily， in optimization。

 things are a little nicer。And we'll see why。A recap of a recall of legal groups。

You remember a league group， a matrix league group。What was it。Give me a one line。

Definition of a matrix league group。The most general definition。Those that。그 down down。그런고 안。

Closed under an operator。That's one property of it， but it's not the definition of it。

Which comes from calling them a group， you right。If it's a group。

Is closed under their matrix multiplication。 So matrix。

Group or matrixtri League group is a group of invertable matrices。😊，That。

Have a smooth operation like matrix multiplication and inversion。As we discussed。For example。

 so long as you multiply rotation matrices。Using that closure idea。You always get a rotation matrix。

But we cannot add them up。And unlike vectors， now， we' are dealing with matrices。

So you remember that the exponential map was very important to connect Lee algebra。

 the tangent of space at the identity to。An element of the group。 It was a series like this。

 And it does give you。They identity。For zero vectoror in the algebra。So we had vector spaces。

 S3 and SO3。As Lee algebras of SC3 and S03。We would use the reation。But really， any of them is okay。

For， for S O3， you could use cross。 This cross notation is also very popular。

 and the matrix version of。Scusy matrix matrix times the vector is the equivalent of the cross product。

We could define the generators。These are。The basis matrices for the le algebra。And if we could。

Construct our vector in the algebra， you think。Some of these generators multiplied by the coordinates。

 Phi 1， p2， and P3。Which this time is correct。 In one of the lectures， I use the negative of that。

 although the negative of it is also a correct basis。

 it's very confusing because suddenly makes the clockwise rotation positive。

This particular version of basis is what we tend to use because the counterclock wise is positive。

So that that was a source of confusion。 It was not intentional。

 I just wrote it off the top of my head and used the negative of these matrices。

And somebody pointed out that the Lee bracket is was。Not giving G3。

 but was giving the negative of that because the convention became left hand。So we learned that。

 Let's not go that way，'s。Use this version of the basis。 So mathematically correct， but physically。

Was too painful to work with it。Now， also， you， you know that this is， this corresponds to Z， Y。X。

 right。Because if you take the。Exponential map。 This will give you。

If I'm writing it correctly for the negative sign。Will give you something like this We be are rotating about the Z axis。

It leaves the Z axis unchanged。For the other ones， it leaves the y and x axis unchanged。

But when we add them together， we consider the simultaneous rotation of these three planes or normal vectors。



![](img/e74251031d2f54abb5b4e1005ad07fd9_49.png)

![](img/e74251031d2f54abb5b4e1005ad07fd9_50.png)

So we。Also。Can write this for S A3。 You will have。3 extra generators。

And the only difference is that we get the generators for X， Y and Z translation。

You're fill in everything else with 0。 Now， when you add them， you get your twist。 This will be your。

Twist in the form that。You are familiar with it。 This will be the ssymmetric part。

 And then you get a translation part。And the transformation was the。Financial map of this twist。So。

 for every。Leee Albra element， there is a group transformation。

 You have this nice one to one correspondences。Ignoring some technicalities for more complicated groups that we're not dealing with them here。



![](img/e74251031d2f54abb5b4e1005ad07fd9_52.png)

We， we always have this。So， this is。

![](img/e74251031d2f54abb5b4e1005ad07fd9_54.png)

We know this much。We want to solve at least a squares problem on matrix league groups。

The problem is that this residual here。Is a function of multiple decision variables。

And maybe one of them is a 3D point， which is not a problem。The usual Euclidean decision variable。

And then maybe the second one is op。Maybe we are also estimating the camera pose。

But also a feature that the camera is observing。And that's what。Slam mins。

Localize and reconstruct the scene what you observe。And maybe we're also estimating another rotation。

 Maybe we are also。Solving for an orientation of for the orientation of an object in the scene。

So in this context of optimization， now suddenly。There's a lot of potential。

To solve many decision variables at the same time， whereas in the filtering case。

Because it gets involved， we tend to aim for a minimal setup that solves a specific problem。

This is more scalable in that sense。Is there a reason。えこ。Should they killed him a medical disorder。

This is an example。 There is no reason for。It's not going to be always like this。 for example。

 it will be like this。Any， any。Inumration of different configurations is possible， right。

So the domain of the residual will be。Direct product of bunch of sets。So in this case。

 in optimization， a lot of time people think about it as， well， S3 ultimately is a set of mates。

 right。It is a group。But it's a set of matrices。Ignoring the algebraic properties of the group that we use extensively。

It's a set of matrices with some condition。And you have a pause。And then maybe you have。Point。

That will give you a domain for the residual。Is this going to be have a different kind of time stamps？

那 youre doing the。Filtering and also smoothie。Yeah， the question is。

 will this have different time stepss， time stamps？Yes。

The optimization formulation is obviously agnostic of that。 But when in practice， we talk about。

Robotics problem data comes in。Com sequential in time。

 And that a trajectory is a discretization of maybe poses at different time steps。

And then maybe we want to estimate0 or drop them。So each of them will be one pose independently。

And together， we will have maybe 100 poses， So the domain will be very large，100 poses。

 maybe thousand points。Maybe some 10 objects in the scene。 you want to estimate their orientation。

Anything is possible here， you define the problem。So。From the legal knowledge that we learned。

 we immediately。Recognize that。This is not going to work if I just add this。Delta each time。

 because as soon as we。Say that R plus 1 equals R K plus some deelta R。

We know that the result might not end up being a valid rotation matrix。 These matrices are。

Operating based on matrix multiplication。 So we have to respect that。In other words。

 matrix league groups are not closed under addition。 We have to multiply。Okay。

 so that's not a very difficult problem to resolve。But given our knowledge， we are aware of。

This modification that we have to make。 An intuitive idea is that。

Move along the curve on the manifold in general， if you are optimizing over a surface。Right， if。

Your objective function maps points。From this surface to some real number。

The domain of the decision variable is that surface。 There is no use for finding a solution here。

That's no， that's not good for。Using it because， well， my， every feasible solution must be here。

On the surface。Now， these league groups are like that as well。 So there is a set。

And we know there are also manifolds， there are surface。 The shape might be difficult to discuss。

 but they are。Main idea is that when you search， move along this geodesics of the surface。

 do not go to the ambient environment。The general theoryorem for this is that your gradient。

 when you calculate it in the Euclideans， you have to project it onto the surface。

If you project your gradient onto the surface in the general case of a Rimanian manifold。

 that will give you optimization on Rimanian manifoldles。So that's a little more general。

 We are working with a nicer case。 It's not any surface。 It's a league group。For legal groups。

 we can use the exponential map。In general。What that map will be。

 You have to look into that specific problem。So that makes league groups。

The next nice case for optimization。This is more general than Euclidean spaces。If you're interested。

 I will share more references。

![](img/e74251031d2f54abb5b4e1005ad07fd9_56.png)

In this part， there's a very nice book by。Professor Bumel， Nicholas B， he is in Princeton。

 He has a book on optimization on Manifold。It's a very accessible book for engineers。

And he has a fearorem there， that。Your gradient will be the projection of the usual gradient we calculate in Euclidean space on that surface。



![](img/e74251031d2f54abb5b4e1005ad07fd9_58.png)

In any case， for league groups we use the exponential map。

And that will perform that projection for us。 That will be the judesic， as we discussed。

 That's the best path in matrix groups。So one problem is that we need to calculate the Jacobian for each decision variable by respecting its domain。

 if it's a point。We linearize it。Using usings the usual first order Tayloror expansion。

 and that will give us the Jacobkubian。She is the partial derivative of the residual with respect to that decision variable。

For example， if your decision variable is on S of3。Now， to perturb the residual using a delta。

We can no longer add a deelta。Instead， what we do， we perturb the current point。

By multiplying the exponential of a delta in the Lee algebra。Does that make sense。

 This is a equivalent of。These two are equivalentent。When。

We respect the rules of the respective domain， corresponding domain of the variable。So x k plus D。

 this is for R N。For any league group， whether S O3 or S D 3 will have X K。Times。Exponential of the。

We don't add， we multiply。Now， y exponential of d， Y not some deelta x matrix。Why not。By the way。

 this K is and I think。Yeah， it's here because this is the it。

Iteration number is not time steps because you can iterate many times for one time step。

 There's a difference。Withwin。Index for the iteration number and the time step。

 We're not talking about the timer step here。 We're talking about the iteration。So why not like this。

Can I just solve for the Delta rotation or deelta pose instead of exponential of some deelta in the Lee algebra。

could be alternative idea。It's because。就他说这个。It real take person。

It'll be on to capture the the delta rotation better。And that's why we't this。Well。

 we can capture in theory， we can capture everything if you just work with the group elements。

It's not because。It's not because it's inferior theoretically。 It is It's completely correct。

 but there's a reason why we work with the Lee algebra。Is it because it's。在就是。You know shouldn。

It we exponential。We can't familiarize it。It is better for linearization。 That's very correct。

 It will make the Jacoban calculations in somewhat trivial。

 You will see the Jacobbean calculations are。Once we derive it， it's always similar。It's。Easier。

 in some sense than。The nonlinearities in the Euclidean space。However， the main reason is that。

We want to use linear algebra。 and that is style of Gaus neutton。

We're not going to be able to use it if we're working with nonlinear pose and rotation。

That's the same reason in the invari IkeF。We are tracking the covariance in the Lee algebra。

Innovation is in the Lee algebra because ultimately， it's a vector space， and we can use。

Linear algebra to manipulate terms。It will be nonlinear， and we do not know how to。

Have equivalent of those nice calculations。Undergroup directly。So theoretically it's valid。

 practically it's nowhere as nice as。Working with the Lee algebra。

I do not have an answer how to do it。Besides having a generic。Non nonlinear solve。So if it's S E3。

 same idea， we're just using a different notation to emphasize。This is a Jacobuban novel。Un illegal。

 not the Euclidean。So typically， when you define pertueb your Jacobubbi residual， what we want to do。

 we want to take derivative respect to this perturb。Term D。At 0。

 that will give a linearization at that。Point x， K。And what's left is the Jacoban， right。

Because the continuous time version of duration is not moving at Delta。

 It must be exactly at that point。And calculus， right？So， we。Now。

 I do not expect you to be an expert in linearization and legal group。

 this is just to lay out the framework。In future lectures， we want to， we have an example here。

 but in future lectures， we want to do this for point cloud registration。

 We want to do it for ourGBD visual geometrytry， and we want to do it for a s。

That's how we're going to do it。So this leads to a general framework。

Of how to solve optimization problems a manifold or lead group。 And this。

Narrative is called framework is called lift， solve， Retract。

Lift because it's too hard to solve the problem directly on the manifold。

 Let's lift the deent of space。Lee algebra here。Solve the problem using， let's say。

G neton or any other optimization method that we know in Euclidean space。Then retracted。

 Retraction is the integration part。 When we want to go back to the manifold。

Using an integration rule。So， lift。Is when we linearize by parameterizing the this delta in the Lee algebra。

Solve。The linearized problem in the Le algebra。 Remember， were after D， D is in a vector space。

For example， it's a twist。And we， we work with vectorized version of it。 It will be an R 6 vector。

Right。The lift， solve。Solve the listed squares problem。 symbolically we write it as matrix inversion。

Whether you know by that， I， by this point， at this point that we're not inverting it explicitly。

Then retract when you retract。We integrate。On legal groups。

 you know how to integrate using exponential。Map。If this was our end， we would just write。

That's the simple integration in R N。Now integration， because this is。

You can think about it as a kind of differential equation。Let's say。X dot equals some v。

Use the oiler integration， using some Delta T time。

This will give you X K plus1 minus minus x K divided by Delta T equals V。

Then we will have xk plus one equals。X， K plus v。Delta T， And then maybe I call。

I'm using subscript instead of superscript， but I mean the same thing。

Maybe you call this the sum deelta。 Now， in the optimization。

 we iterate and solve for this Delta movement， such that all the objectives。

Possibly multiple objectives are satisfied at the same time。これどして。明确的。do on these。

We always do it at 0。That's also。Nice thing in。Working with league groups。

 we always lifted to the Lee algebra。 The Delta is always in the Lee algebra。

Even if we are not at the Le algebra because。This is as if I'm writing R exponential of omega， right。

Omega， the angle of velocityity was in the Lee algebra， in the body frame。

But rotation can be anywhere。So the Delta movement is in the real algebra。But。

The actual configuration is not necessarily。And because we solve for this deelta。We。

Can always linearize at 0。Does that make sense？Like why do we linearize it and save。你嗰是玻璃。

Is it very generic or？This is day。And other situations and value is really important。

So the question is， why do we linearize it at  zero？

And I guess we that was the conclusion that this is integration， right， for league groups。

 you had the equation that we have。啲。That。Equals T。This twist， right？And。

This is called reconstructioncon equation。 You can reconstruct elements of any legalbuing this differential equation。

 and this is the integration。Now， the question is that why we linearize at  zero？

Simple answer is that that's how we define the derivative， because。Theative is。

F of x plus H minus f of x。As H goes to 0。So if you're going to protect the function with some deelta or H。

Yeah， we wanted to vanish when it's 0， what's the rate of change of my function。So， we。

Perturb it with some deelta the year。And then when D is 0， we want to see what's the rate of change。

 which is the Jacobian。 So that that， I think the mathematical reason I can give you is this that。

We want the rate of change at exactly the current point， not by moving to different point。

So Arthur is giving another reason why。To lift the problem that。

Possibly the measurements are in the Le algebra。Physically， that can be a reason too。

If you're receiving measurements in the tangent space， maybe that's what you want。Did do。

But as a general framework， this is a。Generic framework for optimization， Manifold lift。

In the deent space solve retract。 Retraction is when we go back to the manifold。

Sometimes this exponential map is called a retraction map。Or projection map。

 as if it's projecting from tangent space back to the surface。You can give it all sort of fancy name。

 but for us， it's ultimately the exponential map。

![](img/e74251031d2f54abb5b4e1005ad07fd9_60.png)

![](img/e74251031d2f54abb5b4e1005ad07fd9_61.png)

So the Jacobians， unlike what what it might appear， tend to be easier to calculate。

 They are not more difficult。If you practice and then get used to all these matrix matrices that are showing up in a row。

Then the Jehuan calculation is somewhat。Simimpr because it's very structured。

 you practice there set of rules， you follow them， you get your linearization。And usually。

 using algebraite manipulation。Instead of using calculus。

One very common way is that use the first order linearization of the exponential map。

 and that will give you usually the Jacobckuan。We drop all the high order termss。

 What's left is the Jacoban， usually。Alternatively， you could define your。This D。

 to be the sum of individual scalar times， times their' generators。

And then you can calculate the Jacobkuan column by column。

 We did that for the Euclidean case as well。 You could do it here as well， but。

A lot of time we can directly work with。The entire the， D vector。Sometimes。

When you're dealing with a more complicated case。As we will see in the RGBD camera。

 there is a projection model of the camera， and then there is this transformation inside。

So then we use chain rule to。Take the first part with respect to whatever is coming in。 Ultimately。

 there is a point that is coming to the projection model of the camera。

So we take the derivative with respect to that input。

And then that transform point possibly depends on the pose。

Then we can linearize the second part using these techniques。

Viectctorization is always possible if you're dealing with matrices。You can vectorize your matrix。

 and calculate them。But I will use a mixture of。Chain rule and first order approximation。

 And that will be simpler。But these are general advice on how to。



![](img/e74251031d2f54abb5b4e1005ad07fd9_63.png)

Compute the Jacobian if you need to。It个。

![](img/e74251031d2f54abb5b4e1005ad07fd9_65.png)

![](img/e74251031d2f54abb5b4e1005ad07fd9_66.png)

Have question for the share went。For the petation we just。



![](img/e74251031d2f54abb5b4e1005ad07fd9_68.png)

Cs every entry of a matrix onto the record， or we do the inverse of hedge movie。

We vectorize the matrix。Because we are taking the derivative with respect to a vector D。Right now。

Practice how you do it your mind to still go back to。

Independly evaluating each column and vectorizing it。 But in general， this is a technique for。

Calculating the derivative of a matrix by vectorizing it。We， we want。As far as I remember。

 we won't use it， but this。If you see it。It's a way of doing it。This is， in particular。

 very easy to use。So， let's。See how， in general， we can。Linear is a residual that is an elite group。

And that will allow us to solve a pose graph problem。That's the。

Slam problem that there are a bunch of poses connected in a graph。And the measurement。

 the constraints of relative rigid body transformation is called post synchronization。

Or we call it post graph。You remember the Baker Campbell House Dof series。 This was a series。

That was answering this， That answers this question that。If I have X。

 Y and Z in the Lee algebra as matrices。If you。Multiply the exponential of x by exponential of y。

What is the equivalent of。This multiplication。In terms of one exponential。This answer is not trivial。

 because。For matrices， Z。Is not X plus y。Unless。X， Y equals Y， X， unless they commute。

This is not true， because if they're commute。The bracket will be 0。Which is x y minus Y X， obviously。

They're both equal， and it will be0。So。In general， that's not true。And that's。

The result is is famous enough that is named after。Three people who discovered it。

So Z in general will be this infinite series。Which you see the first two terms are x plus Y。

 Then you have one half of the bracket。 Then you have one over 12 of a nested bracket。

Then one over 12 of the nested bracket by flipping the variables。

And this nested bracket keep getting deeper and deeper。 It's never ending。

So it's not very nice to work with。However， it， it unlocks。

The answer that the answer is that we can directly work in the Le algebra。

To capture something like matrix multiplication on the group。

 because ultimately exponential of x times。Exponential of why。Its some。Let's say， R1。Or two。

We're multiply two matrices， let's say， rotation。Or rigid body transformation。

And it's interesting that。This will be another rotation matrix。So， there is a way。

To multiply rotation matrices or rigid body transformation without working with them directly in the Lee algebra。

So the Lee Alzebra of a matrixtri league group completely captures the local structure of the group。

The algebraic structure of it。Add the identity， This is somewhat magical。 It' it's。😊，Very surprising。

 And that's what makes league groups very powerful。



![](img/e74251031d2f54abb5b4e1005ad07fd9_70.png)

So let's see how this will be useful。 by the way， you。



![](img/e74251031d2f54abb5b4e1005ad07fd9_72.png)

So in general， it's way too complicated。 we can't。Bother to calculate so many terms。

They don't have time。To evaluate this， and then also we have to iterate as well。

 and all of that must be very fast。So imagine we could collect all the linear terms。

You can write it as。The bracket will be， of course。X， y minus Y X， right？You just write。

 expand it and then collect them somehow into。And that approximation。That is。

Let's say it will give you X plus。What should I call it。I going call it a。三。Jakubian， right。

 matrix times is y。And drop all other terms。Or or you could talk about Y plus some。Matrix。In general。

 is this possible Probably not for some group， it turns out you can do it。 And there are papers that。

1 paper for S O3 is very easy。 We， we have the results for a long time。 For S E 3。

 there is a T RO paper。 It was one of the references in the legal group lecture by。

Professor Tim Barford， he calculated this for S E 3 in closed form。

Becauseuse there is a cross term in the matrix。It's a little long。Nevertheless。

 we can get the closed form result and all of these closed form results are available in the textbook。

 I will point you out on Piazza to that。In the chapter on groups。So in general。

 it might not be possible， but for some。Nmer is always possible。For S， O3 and S E3。

 at least it's possible to do it in closed form。

![](img/e74251031d2f54abb5b4e1005ad07fd9_74.png)

That's very。Computationally attractive。

![](img/e74251031d2f54abb5b4e1005ad07fd9_76.png)

So。I'm going to summarize。What we get out of that。If you remember。

 we can use the ajoin to shift terms， and we've done it before。If you shift。X。To move forward。

Add the I joined inside the exponential map to be multiplied by the twist。

We talked about it in previous lectures。 if you're moving it to the。Left side。

 add the inverse of the a joint to the exponential。 So using the a joint， we can shift terms。

And otherwise， it's not possible because matrix multiplication is not communicateutd。

And the reason we can do it is just following the definition of the a joint。Multiply them by x。

You get the first one。Turn x to。X inverse and then multiply from left。 You get the second one。

Because if this is true。This could be X inverse。As well， right？If it's true， true for any matrices。

 X inverse is ultimately another group element。 So we could talk about it that way as well。



![](img/e74251031d2f54abb5b4e1005ad07fd9_78.png)

So we know how to shift terms。

![](img/e74251031d2f54abb5b4e1005ad07fd9_80.png)

So the linearization li group is done using B C H formula。 We're not using Taylor expansion。

That would be。A more general way of doing it。 But B， C， H is more。

Lee algebra friendly version of that。Rule number one。

 if both termses are small in the product of two exponential， just。Drop the high order terms。

 approximated using exponential of some of them。When you should do that， well。

 when both them are small， if you don't know if they're necessarily going to be small。

 this is going to be a very rough approximation。 You're dropping a lot of。

Other terms that might be large。So this， this one easy。 and this follows from the first。

Two terms of the B C S formula。

![](img/e74251031d2f54abb5b4e1005ad07fd9_82.png)

No， therere。Actual problem is。

![](img/e74251031d2f54abb5b4e1005ad07fd9_84.png)

What if。Well， if both terms are big， we are screwed。You can't draw up anything。But luckily。

 that's not the case because。If you remember， when we optimize， we are perturbing using a deelta。

 A D that is a small。 So always one of them is a small。So we're in luck。And。

When both of them are are not small， assuming that in this case， the notation you see is small。

And R is your residual that can be large。We are after。Answering this question。You the same。

What is the first order correction。To this R and Casi that approximately will give me the product of these exponential。

Following the notation， we see below， I'll call it A。 I'm going to use a。Still here。

And if we strictly follow the notation， we have to add。A hat。So the question is， what is。

A first order correction。The product of this is exponential， as we discussed before。Now。

 take the log from both sides and then take the V。To make it vector。

So that we can just also ignore this log and we。It turns out for league groups。

 it will be the inverse of the right to Kban and。If。The small firm is on the right。

And the inverse of the left Jehuban if。The small term is on the left。Now， left and right to Kubians。

There are several ways to derive them and define them。 But ultimately， these are。

The collection of all first order terms in that series。Infinite series。

That's how the derivations in the textbook and book goes on。 It's possible to drive。These matrices。

 we do have a close form formula。 I gave it to you on the legal group slides。For example。

 for what is the exponential map of。S O3。Well， you need to expand this。These terms。

And then collect them into terms that show sine and cosine。Seerries。

And then that's how we find a closed one formula。You can do the same thing here。 In fact。

 the Jacoban。For S， O3， well have。I'm gonna not gonna right left and right。 You hold me accountable。

 but it will have something like this。There's a negative sign difference between left and right。

Otherwise， they're similar。Which is a hint to whether。What is I observing frame， right。

 Am I rotating with respect to a reference or the reference is rotating with respect to me。

Because of these two possibility， you get this left and right。Conventions。

So it's an integral of that for SO3。 and that ends up being one integration of the exponential map。

But in general， that's， that's something that if you're interested to dig in it， you can。Learn more。

 but it is solved for。S O 3 and S T3 already， we have the result in。Literature。So if you notice。

 we linearize， but we always know these formulas。In fact， it could be already available for you。

As some functions。Although you linearize for different problems。

 but always the Jacobuban is the same。The left and right Jacobans are related using the ad joint。

I leave more discussions。 If you're interested， we can follow up and look into。Some of the des。

 But I think for now， this is enough to solve our problem。 So we just learned a technique to。



![](img/e74251031d2f54abb5b4e1005ad07fd9_86.png)

Linearize the residual that has a decision variable as an elite group。



![](img/e74251031d2f54abb5b4e1005ad07fd9_88.png)

An example that is not computational。Consider a residual that is a function of x1 and x2。

 X1 is a 3D point。 X2 is a rotation matrix。The delta that we want to calculate has a D1 term for the point and has a D2 term that we integrate using the exponential map for the rotation part。

If we linearize this problem， there will be a Jacobubban for D1 and another Jacoban for D2。

In the Le algebra。The Jacoban of the first one is。So we pertubed these variables 1 at a time。

 and when we perturb the variable respect to x1， and we differentiate with respect to x1 following their calculus rules。

All other variables are treated as constant。 So we are not worried about the domain。

They're just constant。This will give you the first Jacobkuan。For the second one。

We pertubed using D2 and evaluated a 0。 This will give you the second Jacoban。

 So this was the lifting part， lift。Solve the resolving。Lar rise leads the squares problem。

So the outcome of this part is knowing D1 and D2。Then retract and the retraction for each decision variable follow the rule for the integration。

 the 3D point just added。For the rotation。Use the exponential map to integrate。And then。

Itererate until a maximum number of iterations or convergence。

So this is a generalization of at least the squares problem to lead groups。Now。

 something more interesting。 This is called Pograph in Islam s。



![](img/e74251031d2f54abb5b4e1005ad07fd9_90.png)

There is a sequence of robot process。There' the initial。Point。Py 0。

Which can be the identity if that's your initial yes。Remo。And then we are at this point。

 How do you get this edge。As。An S 3 measurement， this can come from， for example， visual oometry。

 point registration using Lidar， maybe oometry。Maybe you have a filter for a state estimation。

Somehow， you can track the pose of the robot。So， that。Measurement here， if you call it Z。

It is also part of S E 3。What you could call a you， maybe。T1， the way we track。

 we track with respect to the word frame。 therefore T1 is T 0 time u。

So this relationship exists between these two nodes and the relative poses。You could consider noise。

 as well。But this defines a model。That connects these two nodes on the graph。Similarly。

 we have the same condition here， here， here。Until T 5。Now， these are。Conseive links。

 edges in the graph， they usually come from tracking or oometry。

There are non consecutive edges in the graph。For example， T 5。Is connected to T 3。

And T 5 is connected to the initial node。In the context of。Slam， we call。你。Loop。Closures。

The loop closures are non consecutive constraints that connect。Notes， they're not。

Sequential in time in the sense that there's exactly the next time step。

And they're very important because without loop closures。

 there is no way to remove the drift from this tracking。 if we only track and connect these edges。

There's no way to remove the drift。In practice， this can come from place recognition， for example。

 computer vision techniques can detect the place and then once you know that you are revisiting the same place。

 that means there is an overlap between an image that I see at T5 and the image I saw at T0 now using maybe some computer vision techniques and image registration。

 maybe I get a pose。First， I detect it， and then I established a geometric constraint。

 And that constraint， if it's supposed， it will give me。A measurement， for example， here。

 if I call a Z。That is also in S E 3。So， no matter。How I get these edges。

 It ends up being a graph of。Process。 So each decision variable is in S E 3。

 My measurements are also in S3。In general， it doesn't have to be this way。

 but this is called pose graph。Because we only have poses as the variable。

Or another name for it is called is pose synchronization。If you only have rotation。

 it it is rotation synchronization。Then， we have。So in this case， we have。

Let's say you could write tea。5 is。T 0 times Z。 Of course， its possible the way you define Z。

 you could have T 0 equals。T 5 s z。So， the implementation implementation。

Is it hard coded that the post T5 can， for example， observe？T3 and T0。

 I'm assuming this is not the result of just running cost statement。These corresponds of hearing。

This is a simulation。 I am generating the graph myself。

 So I decided that I want to add these loop clos in。Reality， the front end of the Islam。

 as we will talk about it， is responsible for constructing this graph。

And it's important how you do it， Because if these ages are wrong， if they're outliers。

Then your solver might break down， which is the importance of having an Mestimator。To。

 to some extent， ignore wrong edges。It's not going to be perfect。 The image processing part。

 registration part and tracking part in the front end。Necessarily， in practice。

 you might add some out playersers。Once you construct a graph。This is just an optimization problem。

 that we talk about it。 That's the back end of the slot。

The current slam paradigm is front and back in front end。

Its the messy part that processes all the raw data to build this graph once you know the graph。

It's very principled。 You just solve an optimization problem。So， G T Sam and。G2 O， R。Slam。

Back in libraries。They solve the graph optimization problem。

And they support different residuals and GT assembly called factors for。Different measurement models。

Whether it is IMU， it's studio camera， monocular camera， pose， rotation。And so on。

So these libraries deal with the backend。You are responsible for processing the front end。Theoro。

Success to the libraries like Or slam。They provide all the pipeline。They take your raw image。

 they process the front end， they build a graph or the s is using G2O inside or graph optimization。

So they do a lot of heavily engineered tasks to solve the problem in a way that it works。

It's not perfect， but。It is the state of the art and feature based the s。

 because it's very difficult to implement a system like that。That it works。

 And a lot of data set it works。 And that's why the community value that work。So much。

So it gives you the front and and the back end。But more on this， we will talk about it more。

So this is， so this will this should draw a map that we are talking about the back end and a particular type of back end when the graph is。



![](img/e74251031d2f54abb5b4e1005ad07fd9_92.png)

Oppo graph。

![](img/e74251031d2f54abb5b4e1005ad07fd9_94.png)

So how to solve this problem。Now， you do not need to solve this by hand， because you can basically。

Use the GTC API or G2 API to implement this。And it will solve it for you。

But it's nice to know what's going on deep down。There's no one way they might choose different way of approximating linearizing。

 but。This will。Clarify how it's done。So the process model for。He friends， this。Nots in the graph。

 we tend to call them keyframes。Because for example。

 you add a node to the graph maybe every one second， or with some criteria。

 you decide I need to add a node。Whereas between two key frames， you might have many images。

 many frames。Out of all every 30 images， for example， you get， maybe you just add one keyframe。

That's why it's not a frame。I determined the keyframe is it？Maybe like the number unique need to you。

さ。Question is， how do you？This is a question for future lectures。 But how do you define the keyframe？

 That's an existential problem。You can set a threshold on time。You don't want to go too far。

 You can set it threshold and the overlap between detected features， You tracking。

 You can set it threshold on the magnitude of。Twist the deelta poses you move， regardless of time。

You can set a threshold on the number of features that you lose when you track。

Probably you don't want to rely on one， maybe list of 4，5，6。Condition to make sure。

It's not too soon because if it's too soon， you're wasting resources。 This graph will grow。

 and then it will make the problem heavier。If it's too slow， you're risking the。

You're risking the you're increasing the chance of failure， because then。

It makes the problem harder to solve。So that's why most people like to work on their backend。

And they write papers and that。And they pretend front end is okay。But front end is not okay。

They keep a face in the paper。That it was easy to get the graph。

So one thing that I find personally attractive that。

Having something like deep learning for end to end。Processing you have something like front end。

 when you just have too many rules and they're just arbitrary， it's nice。However。

 deep learning base front endends at this time tend to be。Sftering from generalization problem。

 because they can work on particular data sets。 But you do need to train them on。The domain you use。

But eventually， it will be nice to have something that is less hand tuneed and more automated。😊。

That will make a good combination with this backend。

And then how to bring in the learning side to the back end is also ongoing。Research。

You can search the paper N F I Sam。 That's interesting。They are using a normalizing flow。

 which is a modern Bayesian inference technique。 and combining it with IM。

 which is a solver for a slam。 We talk about it in the slam lecture。AndI'm going to plan this。

All rightBack to the example。So the process model between keyframe J and I。

 and they are not necessarily successive keyframes is Xj equals Xi times Ui。If it's noisy， of course。

 we have this。Exponential of B， K。Notice that this is a time difference equation。

 It's not a continuous time。 So the noise。Is multiplicative with an exponential map。And as usual。

 the noise is a0ing Gaussian。And。Lee algebra， take the log of。So。Define the residual here to be。

By isolating the noise， then we define the residual to be。Inverse of this function。Times。X J。

 because it's a matrix。Take the log of this and then vectorize it using V。And the process model。

 the residual is defined as u inverse times X I inverse times X J。This supposed to be the identity。

 When you take the log of it， it's supposed to be 0。That's when the constraint is satisfied。



![](img/e74251031d2f54abb5b4e1005ad07fd9_96.png)

To linearize。Pert。Now， you， you can per from left or right， and that both are perfectly fine。

I'm doing it from the right side。 You can do it from the left。

Sometimes it's easier from the other side。 So perrb。X I。All the nonsense you see here。

 I'm just using the a joint to shift all the terms to one side。And shift this delta to one side。

 rather left or right。Once you have this， we go back to。Remember， this is the residual， right。

And this is the。Or。

![](img/e74251031d2f54abb5b4e1005ad07fd9_98.png)

The Delta。Then， from here。I know what to do。Because now I isolated the residual and the deelta term。



![](img/e74251031d2f54abb5b4e1005ad07fd9_100.png)

This looks like the first one。 So what I get is。

![](img/e74251031d2f54abb5b4e1005ad07fd9_102.png)

The first part， whatever it is， the residual。Minus inverse of the right to K N。

And the residual is this input times。Whatever is inside the exponential， which is there， I joint of。

X J inverse times X I times C。 Now， this needs some time。 you need to。Think through it。

 But this is the result。And the negative here is because of negative here。

So I have successfully linearized and what you see here is my Jacoban。

The are joint is showing up because of shifting terms。Do it for Xj in a similar fashion。You get。

You don't need to shift them。 So we just get the。Invest of the right to Kuban。

So it's more principle in some way to linearize。

![](img/e74251031d2f54abb5b4e1005ad07fd9_104.png)

Resual。And then you will see that I'm solving Gauss Newton in the code。 And take a look。 Let me know。

If you have questions。

![](img/e74251031d2f54abb5b4e1005ad07fd9_106.png)

Try to connect it to the driverss。 Now， this particular problem has more。Structure。

 you cant solve it using optimization techniques。In a global way。 And this is the work。

Of Rose and Carlonne and John Leonard from MIT。It's called E S。

This solves a synchronization problem up to some noise level and solves it globally。

But this particular work， is's not robust to outliers。 So in practice。

 you still need to have it in a robust way。But as you think， when it becomes robust。

 it will be a very nice backend。

![](img/e74251031d2f54abb5b4e1005ad07fd9_108.png)

That solves the problem globally optimally。

![](img/e74251031d2f54abb5b4e1005ad07fd9_110.png)

So there's a last example that I。Quickly go through it and leave it for the point cloud registration。

Lecture。But this is a point cloud registration problem when we want to minimize a distance between two set of points when one of the said here why。

All of them is transformed by rigid body transformation so that it gets aligned with。Point cloud X。

So， ultimately， this is a。Les the squares problem and this notation in this case。Means。

When you factorize。This covariance weight with choli ski。 You get LL transportpose。

 So the residual has this form。We define this to be R。The goal is to minimize the objective function。

And find the rigid body transformation。If I want to solve this using Gauss neton。

 I need to find the Jacobian。Once I know the Jacobkuan， I can just solve the problem。

So to find the Jacobuban， in this case， it's easier to perturb from the left side。

You can try the right side， and see why。This is easier。So you can ignore， these are just weights。

 right， you can ignore hell。So perturb the pose and apply a first order approximation of the exponential map when you do that。

You can separate the residual， plus。This extra term， this extra term。Where I define T。

Times y to be just another point， Z。Is showing the Jacobubian。



![](img/e74251031d2f54abb5b4e1005ad07fd9_112.png)

So the Jacoban in the way， in the same way， we find the H matrix in the invariant A KF。

It turns out that if。I find a matrix that when Im multipplied by cassi as a vector。

 it will give me the same result as the left hand side that will be the Jacobubian。So。

 expand the twist。Do all the manipulation and what you find is this result。

We'll go through it in future lectures for different problems again。

So we call this Jacobban is 3 by 6。And that's how you can linearize and find the Jacobubian。

So no calculus， just algebra and first order。Approxiation of the exponential map。 So in my opinion。

 this is。So much nicer。

![](img/e74251031d2f54abb5b4e1005ad07fd9_114.png)

So that's it for today。