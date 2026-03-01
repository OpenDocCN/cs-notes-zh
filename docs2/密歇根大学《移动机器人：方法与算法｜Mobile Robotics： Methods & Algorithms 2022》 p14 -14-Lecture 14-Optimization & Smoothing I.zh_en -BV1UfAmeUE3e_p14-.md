# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p14 -14-Lecture 14-Optimization & Smoothing I.zh_en -BV1UfAmeUE3e_p14-

Welcome to。

![](img/4b0d43562f19c84b95d59cff043c83c1_1.png)

The lecture on optimization and smoothing， this is the first out of two lecture on this topic。

And we will focus on， on linear at least squares problem。 We're going to build up to understanding。



![](img/4b0d43562f19c84b95d59cff043c83c1_3.png)

A class of problems that we can solve using。A Na linear lease square solve called Ga Newton。

And it's extensions。We're can establish some notations。 We say a matrix is。Positive definite。

Or semi positive semi definite。If。You see this notation that a is。Greater than B。

 that means a minus B is positive definite。Now it's carely bracket。

 maybe you just use the sorry carely inequality， you can use just normal notation as well。

 inequality， it doesn't matter。So that means that a minus B will have positive eigenvalues。

The two norm， which is the Euclidean norm。We can show it with this notation， just a plane。

Norm notation， or maybe you put two in the bottom。Which is the same thing as taking the dot product or x transpose X and taking a square root of it。

L1 norm is some of the absolute values of vector x。 This is also called L2 norm。Let's call L1 norm。

In general， LP norm is。Calculated by raising the absolute value of each entry of the vector。

 the power of P and then taking。power the sum to the power of1 over P。

And the dot product or inner product。Any of these notations mean the same thing。

And the Norball is a neighborhood centered around X C。Less than a radius R if you see this notation。

Now， generally， you can define the ball using any of the norms you want。

 It doesn't have to be the Euclidean norm。But if it's not to state that the default plantation is the Euclidean norm。



![](img/4b0d43562f19c84b95d59cff043c83c1_5.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_6.png)

We're dealing with an objective function that takes a vector in R N and gives you a real value。

The argument of this objective function is called a decision variable or design variable。

 We wish to minimize this objective function and find the value of x。

That minimizes the objective function。 So then x， that minimizes F is our solution。

 If the solution refined obtains the least amount of value for the function。An entire domain。

 that's a global minimum。If it's in a neighborhood， we call it a local minimum。



![](img/4b0d43562f19c84b95d59cff043c83c1_8.png)

For example， here we have。

![](img/4b0d43562f19c84b95d59cff043c83c1_10.png)

Local minimums。And we have local maximums。This is the global maximum。And this is， of course。

 the global minimum。

![](img/4b0d43562f19c84b95d59cff043c83c1_12.png)

We're going to need some structures that。We can calculate for continuous functions。 In general。

 we assume the objective function is a smooth and continues。

 That means we can differentiate the function。The first。Dirivative of the function。

 which is a vector。It takes a vector， and it gives you。A real number as the output。 Therefore。

 when you calculate the derivative， this is called a gradient， which will be a vector。

Of partial derivatives of the function。Now， sometimes this is a row vector。

 But if you're working with column vectors， you can stack them in a column。 It's not that important。

 That's a choice that you can make。But if you strictly want to follow the definition that will show up in the Jacoban。

 this is a row vector。But we tend to work with column vectors。

So the gradient is a vector of the same size as your。Domain X。 So this is an n by one vector。

Or sometimes we write grad F。HesciN is a symmetric matrix。Of second partial derivatives。

 It's symmetric because because of the assumption that the function is continuous approaching。

The derivative。Of the derivative， right， This is the second order derivative。

EN is the Jacoban of the gradient。So approaching the derivative of the function。

And different orders should give us the same answer。 Otherwise。

 it violates the condition of differentiability at that point。 Therefore， by assumption。

 this must be satisfied。 and Hes N is a symmetric。Matrix and the diagonals are。

Second derivatives for the same variable。Now， using Taylor's theoryorem。

 we can approximate a continuously differentiable function and analytic。

 That means up to the order we want， all the derivatives exist。😊，And locally。

 will converge to some functions。 It's not gonna。Explode， the derivatives exist。

 and we have convergence。So we can approximate our function using。At polynomial。

And the way it works that the first part is the linearization of the function。We are。

Writing the expansion about X。Using a delta that we call D。

So the approximation of the function has a linear1。

 which is f of x plus the gradient transpose times d。Which we talked about this。Sometimestime that。

This， in fact， is the differential of your function。And what is basically saying here is that。

My function up to first order。 If I move a delta at x is the value of the function at x。Plus。

 a differential， a Delta in the function。And this differential， of course。

 is in the infinitesimal sense calculus。Which is exact， exact linear movement。Similarly。

 we can talk about the second order polynomial approximation， then of course。

 the second order derivative will show up， and that's the Hessian matrix。

Then we can have a quadratic approximation of the function up to having the second order derivative here。

And then we can drop the higher order tax。You can generally do this up to any order。

 but it's very complicated to calculate。Third order derivatives and higher than that。

We are talking about our N and Euclidean spaces generally if you。

Come across works that deal with manifolds and care for the spaces。

 this notion of inner product will change。So， they gradient。

In a lot of context is called Riman gradient because the metric will give you different directions based on how the space is curved。

But we're going to deal with Euclidean space， flat spaces。 This is the usual characteristic。



![](img/4b0d43562f19c84b95d59cff043c83c1_14.png)

Oh no。

![](img/4b0d43562f19c84b95d59cff043c83c1_16.png)

So the local quadratic approximation of the function。Can be retain like this。

We will need to calculate the gradient and the hesian。 You could sometimes you see this form。

 which is a change of variable。F of x around x 0 is F of x 0 plus gradient times at deelta x， right。

Both are fine。Depending on what you want to do， you might prefer one notation or the other one。



![](img/4b0d43562f19c84b95d59cff043c83c1_18.png)

So from Calcu was the first order necessary condition to find the extreism of a function。Is。

Done by setting the gradient to be equal to 0。So the first order necessary condition。

Is this Find the roots of the gradient。The second order necessary condition is。That the HnB。Positive。

 semi definite。Because we want to find a minimum。The eigenvalue values of the Hesstrum being non negative means that we have convexity in a local neighborhood and that leads to a minimum。

If it's the opposite， it's negative。Definite that corresponds to a local maximum。

But we always minimize。If we want to maximize， we just multiply the objective function with a negative sign。

The second order sufficient condition is when。All the eigenvalues are positive。嗯。

And if you have mixed signs， that's a saddle point。 And it's generally。Not a good situation because。

We know， that's not。There's a solution better than that。 We already know that。

The test is inconclusive。 You can go to higher order derivatives。 There are more tests。

And you can find out what direction you should move。



![](img/4b0d43562f19c84b95d59cff043c83c1_20.png)

But fortunately， we're not going to talk about。

![](img/4b0d43562f19c84b95d59cff043c83c1_22.png)

Those the stuff。So another structure is convexity if we do come across an objective function that is convex。

The local search will give the global solution， and that's very desirable。However。

 we will see that in our linear of squares。In general， might not be convecx。Sometimes it。

 Sometimes it's not。So the function is convex when you。

Pick two points and interpolate using a theta promptter。That line is always above the function。

In other words， if you pick a point and linearize your function。

 the line is always below the function。It's never the case that the line intersect your function。

In general， a set is convex。 If you pick two points and connect them with a line。

 the line never leaves the interior of the set。 That's the convex set。

So this condition is the same thing as if you linearize your function。Your。

 the value of your function is always greater than or equal to the line that you approximated at that point。

And the second order condition for convexity is that the curvature。

 the hesian is also showing geometrically the curvature， these eigenvalues are non negative。

 we have positive curvature which causes to have this bowl shaped and convexity。



![](img/4b0d43562f19c84b95d59cff043c83c1_24.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_25.png)

So the first problem we should talk about is the linear list of squares before we make it a linear。

Because the nonlinear methods， often。Solve a linear sub problem， and they iterate。Due to。

Linearization。 So if we can solve the linear case， then we can come up with an idea to solve the nonlinear problem using linearization。

So a linear least squares problem is generally a problem that you have a linear system， AX equals B。

A is a tall。The skinkinny matrix， more， more rows than columns。And full column rank。

 that means all the columns are linearly independent， these are the assumptions。In practice。

 B is never in the range of A。Because of noise and all imperfection in the data we observe。

And generally speaking， this corresponds to。The measurement。And this is the model。

You remember in a common field ring， we had。Z equals H x。So that matrix A is the model。

 is a sensor model in this context of perception and state estimation。Wereub an assumption。

 but it still is a model that we assume。And the vector that is the right hand side of A X equals B is something that we receive。

 obtain。By sensing。So because of this imperfection， we define a residual。

Which is the difference between model and the measurements。 And then we aim to minimize。

The norm is squared of this residual。 So the residual is a vector。

 You take the Euclidean norm is the sum of。Squares of each term。 And then you。Basically。

 minimize that， right， because norm takes the square root When you raise it to the power of two。

 you drop that the square root。 So basically， this is。One half。

Some of r1 is squared all the way to R。How many。It's a question for you。And。Or M。And。N or M。

You have to say louder。M。Okay， so a is a map from。R N to R M。 So R will be。M dimension。

A is a map from。That acts on a vector that belongs to R N。And gives you R M。

So the gradient is we just go ahead and calculate the gradient of this quadratic term。

If you don't know how to do it， you can Google Matri calculus。 That's a website。

 You type your objective function。And I will give it to you。

So the gradient is a transpose times a times x minus a transpose B。The hesM is。Constant。

And it's quadratic。 A transpos a。If all the columns of a are linearly independent， of course。

 will be positive definite。

![](img/4b0d43562f19c84b95d59cff043c83c1_27.png)

Sa if you're looking to。The first order condition。Symbolically， we can write the solution as。

A transse a inverse times a transpose times B。And the second order condition is telling us that。

By assumption that a is full rank， this is positive definite。 Therefore， it is invertible。

In other words， you can say the determinant of a transpose a。It's not 0。And because it's quadratic。

 the eigenvalues are always。No negative。Then we arrive。



![](img/4b0d43562f19c84b95d59cff043c83c1_29.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_30.png)

Set this equal to 0。 This will give you the normal equations。

 So the normal equation is from the necessary condition。

We do not invert a and we solve this using two methods。

 usually Cho as key factorization by factorizing a transpose a。Because Chaki requires a square。

 symmetric， positive， definite matrix。Or we can directly factorize air using QR。



![](img/4b0d43562f19c84b95d59cff043c83c1_32.png)

So this is a global minimum because。The second sufficient second order condition is satisfied for this problem。



![](img/4b0d43562f19c84b95d59cff043c83c1_34.png)

Example， we had an example of target tracking。 We used different filters to solve this problem。

The filters， of course， were solving the problem reccursively in time。

You can make least the squares recursive as well， the linear case will give you the same solution as the linear command filter as you verify in your homework。

Or a problem。We are talking about a batch solution。We have the entire data。

 and I want to just solve one list square problem， given everything。To。Compte the trajectory。

 And because I have all the information， the future information can be used to correct the past past estimates。

And this is the smoothing problem， as opposed to filtering。Hence， we call this a smoothing。

 So this smoothing is usually in form of optimization。

 or at least a window in time that processes data。So target tracking using smoothing。We deal with。

 it's the same problem。 We have a linear。Motion model。

 because we don't have any knowledge of the target， how it moves in the plane。

The measurement model is。Linear， we get directly。2D coordinates of the targets。



![](img/4b0d43562f19c84b95d59cff043c83c1_36.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_37.png)

So you have to formulate your。Resual。And then you can stack all your residual。f。One time a step。

And then you stack them for all the time， step。When you do that， you get。

We construct the linear system。 They will end up being informed of that A X equals B。 now x is。Here。

X 0， x 1。X， and whatever is the number of data。So the variable that you see。

 the long vector is the entire trajectory discreteretized at different time steps。

This is a simple problem， but the exact same thing will happen in Islam。

 It will just get more complicated because at every time step， we have a。

Then we might be dealing with position orientation。Possibly some other parameterss。

So the trajectory is discretized。Particular time steps。

 we stack them and we want to estimate recovered the entire trajectory。Why do we define our。て没。リクスして。

Is that just to kind of extract information to the motion model？Because in general。

 we have x k equals f of x k minus1。RightSo the difference is the residual。Noise is  zero mean。

 What I'm doing I I'm actually taking the expected value。 That's the mean。 So the noise is 0 mean。

Okay。And the measurement difference is， in a similar fashion。We did in。Filtering。

 basically the innovation term here， we call it residual。So in the filtering。

 we would predict in the context of base filter， predict and correct。Here， we just stack everything。

 we treat。The motion model as another form of。You could say observation， data。

But it's a different type of observation。 Usually it's not perceptual。 It's not from the environment。

 It could be an assumption。 It could be a model。 It could be a prior。Maybe it's IM U。

 It's usually inform of proper reception。Here is an assumption， right？

How do we formulate it from R to a， that's the good question。

 that's why you should look into my code。They provide it。But， generally。When you stack。

All these residuals。If I do it only for these two。Whats what is my state， you don't have space。



![](img/4b0d43562f19c84b95d59cff043c83c1_39.png)

So the motion model is telling me that I have negative of identity and identity。

The observation model is telling me， I have。0 and H。The right inside。Supposed to be 0。

And this one is supposed to be the measurement。Okay。I only have two variables here and two equations。

Typically， for one equations， we get one from a motion model that correlates。

The variable with in two time steps， and the observation is for one time step。

And let me thank all of them。This will grow， right？It's not going to grow just in。Number of rows。

 but because we add more variables， the columns will grow as well。Does that answer your。Question。我手一。

St。What is the expectation for when do？We want to solve for this vector。That's the goal。

RightThe same same goal that we had when you implemented a column filter。Right。

So the objective is to find the design variable， decision variable， the state variable。

 they all mean the same thing。

![](img/4b0d43562f19c84b95d59cff043c83c1_41.png)

Now， we recognize that this is a linear list of squares problem because it leads to a X A X equals B。

 If you solve it， it will nail its trajectory and it will be smooth。 It won't be jumpy because。

We just solved everything all at once using a linear ista squares， which in Matlab or Julia。

 you just once you form A and B X is basically a back slash B。That's all you need to do。跟来。对呃。就你想发过嚟。

Or the end， we saw something that very similar to be previous equate to the most recent equation that you。

They like putting your programming。就食街嘅。Like his Whit program。No。

 we are not talking about linear programming here， linear programming。We could。

 but it's a little off topic。 at this point。s that's the problem of having a linear objective function and linear constraints。

We're talking about unconstrained problems。Now， point out one of them is actually constrained， but。

We can convert it to the way you see I'm doing it。But this is the context of unconstrained。

Programming， optimization problems。Linear programming is the first。

Usually entry level topic to constraint program。 There is a course It will be taught in fall。啊有异议。

I think 6，11 by professor。At他。I highly recommend that because is's an expert in that area。

 he will teach you nonlinear programming。 He will talk about linear programming。

 quadratic programming。Comvex programming， in general。Generalization of that SDP。

 semi deffinite programmings， when you deal with matrices。

We're not talking about those of stuff here。

![](img/4b0d43562f19c84b95d59cff043c83c1_43.png)

So if you。To stack all the variables。 As you see， we have 400 lines。Rose for the matrix。

And 200 variables。So 200 variables， because each variable has。Two coordinates， right， in the plane。

 it's like x1， x2。And I have 200 So that means， it's100 steps。This is hundred times steps。

When you visualize the matrix， you realize that this is a sparse matrix， because。

The total number of entries is 400 times 200。Which is 8，80。Thousand。Entryries in this matrix。

 That's a large number。However， only 604 of them are non zeros， everything else is zero。

So it's a tiny fraction of this matrix that contains information。 The rest is just。

Placeholder for making sense of that matrix representation of the equation。

So we usually do not construct this matrix explicitly by filling in zeros。 You can use the sparse。

Marices， to。Only fill in the nonzero terms。Okay。That will be very memory efficient。

A transpose a preserves the sparsity， although you can get many patterns here because it's a simple problem is's band diagonal。

It's not only diagonal it has a thickness here。 So it's a band diagonal matrix。

And its still it's a sparse。When you factorize A using QR。This is the。

Oper triangle are matrix that looks almost diagonal。Also， when we factorize Choli ski。

 the L transpose has a similar form。 Now， in Islam。

 you will get more interesting patterns of sparsity。 The shapes will be more interesting。😊。

This is because it's a simple problem。We don't have。Basically。

 connection between a variable at time is step 10 between a variable at time is step 1。

 So there is no nonze entries in this a transpose a or the a matrix。

And it'slam because of the loop closure。 suddenly you get。Nonze terms here， right。

 because variables at totally different time of steps can get。Correlated。

The sparsity pattern will remain， and that's a very important factor。

And solving the problem efficiently。Why， because factorization of any of these matrix factorization roughly。

If we ignore the small differences between different methods， they scale cubically。

When it's a sparse， usually we can do it in linear time。



![](img/4b0d43562f19c84b95d59cff043c83c1_45.png)

When in this。Level of sparsity that I'm showing it， it will be linear in time。



![](img/4b0d43562f19c84b95d59cff043c83c1_47.png)

What's the咩 fine。No zeros。So I have a matrix， right，1，2，0，0，0，0。I make a plot out of it。You have。

Columns， you have robes， right。You have。Well， this is not like this because this is my zero， right？

Or one。So I have。A dot here， A dot here。 I don't have do anywhere else。And。Math lab。

 you can use a spy。Function to visualize。There should be a similar function in Julia and Python as well。

So we don't care about the values as long as there is something in that entry。



![](img/4b0d43562f19c84b95d59cff043c83c1_49.png)

A more interesting example。That they might teach you in machine learning courses。

Linear regression with L2 regularization。We're given a data set and data points。

The data points out in form of their inputs and the target values or measurements。

X I can be a vector of Rn in general。And the target values are。In this case。Scaalar。

Because the target values are continuous， the outputs， we call it regression。

 if they're discontinuous， it's a classification problem。Now， we want to build a linear model。

 So we assume it's structure for the model。The function that we want to approximate is of this type。

 which is a weighted of some basis function。If。Its linear basis。 This would be。Like this。 Basically。

 we're trying to feed a line or plane。But that's not interesting because data might be nonlinear to be used on nonlinear basis。

 It is it is still called linear regression because the function is linear in weights。

 Wes are the unknown variables。 The basis function， although they're nonlinear。We will evaluate them。

 There will be just numbers。So， the function， y。Has this form。 So it's a function of x， if we know W。

Therefore， if we no weight for any new input X， we can evaluate the function。

 So we constructed the model of the function。But we don't know the weight。

 but we're given data from data we want to estimate。The weights W。So you can write this also。

This way， or。Anyway you like， they all mean the same thing。

So the W itself is a vector of stacked individual weight。So we have n data points， right？

And we construct the function that make the function makes every input a basis。

Which you can assume if we can see that if we have 1 million data points， of course。

 we're not going to use this method。So we have W0 to WN and similarly。

Phi is a stacked vector of individual basis functions。Typically。

 we choose the first basis is 0 to be one。And because of that， W 0 is called the bias parameter。 Now。

 if you're truly dealing with linear basis。Let's say it's a 2D example， right。

 This 2D example linear basis。 This is a line regression。Linear in 3D， this will be plane regression。

So if you don't have bias， all you can do is finding different lines that go。Through the origin。

 So without bias， there will be no feeding to data。So you will need the bias。So， you can learn。

Actually， what's going on in the data？Now， this gets a little blurred once you make their base nonlinear。

You can still recover that。Because somehow the optimization can figure out to make one of them。

Byers or mixture of them can shift that to。A different place。

 in any case is customary to include is still the biast。So the first basis is one。

You can have many options for the basis。One default model that people use is the Gaussian or a squared exponential basis。

In the context of neural networks， this is also called radial basis functions， RBF kernels。

So it's the exponential of negative of。Difference of input x with the center of this。

Bump or Gaussian shaped basis。Divided by。Some bandwidth。 This is the kernel bandwidth， I mean。Beyond。

That certain region will be 0。 So the bandwidth controls how wide this basis is。 If it's a small。

 the influence of the basis， of course， in a small neighborhood。Ithi was too large。

All the bases will get mixed up。And this is called S is called hyperparameters because it's not directly the parameter of the model。

 W is the parameter， and this is a permetric model。



![](img/4b0d43562f19c84b95d59cff043c83c1_51.png)

So we want to solve this using list squares。So given that we have the bias term。

We have n plus one data weights。Although we have n data points。

So this will be under determinement because we have n plus bond variables and measurements。To to。

The truth is that this will be a minimum norm problem。 That means we should minimize norm of W。

Subject to。This linear constraint。But the equivalent problem using methods of log range multipse will be this regularized problem。

So， it's customary to。Amission learning literature to just write down the regularized。

Le the squares problem。 This term is called regularizer。

 You can choose any regularizer that you want。The role of this is that to enforce。

The search to find the smallest， smaller weight that will solve。

 that will satisfy the main objective， okay。So this is different than the lands。

Your question is too broad。 is Lada is used for reducing overfiing。 Yes， it can be because。

It's a trade off。Yeah， it's a concern。 You don't want to overfit。

 So you have to find a good value of the lambda。So we can stack these。Individual terms into a matrix。

 Now we have a linear system and is' also regularized using L2 norm。

And the matrix phi is called design matrix。 It's an n by n plus one。

Because each row is basically one。F one。X1。Fe。And X1。

 So we turn every input to a center of a basis function。 and for。

Every basis we evaluated using all other points， including itself。

 that will lead to this design matrix。

![](img/4b0d43562f19c84b95d59cff043c83c1_53.png)

That's basically your A matrix that we had。

![](img/4b0d43562f19c84b95d59cff043c83c1_55.png)

How to solve this。 Well， this is all the smooth and nice。 It's a quadratic cost function。

 Take the gradient。That will give you three transportse p times W minus v transportse T plus。

Lambda times W。 So those onehals are。Include to keep the gradient pretty。

Use this first order necessary condition you get。This solution。Again。

 of course we want inverted explicitly。 So it's interesting that when you regularize。

Your normal equations。Takes this form。As opposed to not having this extra term here。

So the role of regularizer is doing this。Changing the。Left and side of the equation。

We will talk about it more， more on the effect of this will come later。



![](img/4b0d43562f19c84b95d59cff043c83c1_57.png)

Now， I have a code example for you。 You can look into it。

But what's going to happen is that given the training points， we use them as basis。

I know the true process， of course， because I'm simulating it。 That's the blue line。

We can fit a function， the dashed line that。Can approximate our function fairly good。

 This is a data fitting problem， basically， but a function is like nonlinear。

 So we need those linear bases。And the weights that we calculated are。Like this。W1， W2。

 some of them are negative， some of them are positive。

You can play with that lambmbda to see how it will affect this。If you change the parameters。

 you will get different solutions。Now， if you work with deep learning。

 you could try to build RBF networks to solve the same problem。 That's also very interesting。

Are you constrained to have having to have the same number of weights as the same number of？

要你得嗰啲 direction。The question is， do we need the same number of weight as the number of inputs？

That is a little limiting， because。First of all， it's not a scalable。

 This is still a very good method。 This is， by the way， it's the second project of Rob 101 course。

 They fit a surface to precipitation data in aka and then they recover the surface。

 The true method for regression is。😊，A little fancier version of this family of method， done by。

Authorities and that state， and they put it publicly available because it's government data。

 we can access it。So that's。That is used in practice。 It's not useless。

 but it's very limiting because what if I have 00000 points， the system is going to be super large。

We can down sampleample， that's one solution。Right， so you need to pick some bases， right。

Every basis you pick， then you need to wait for it。So if you choose to have less weights。

 that means that you need to cut some of the basis functions。The deep learning variance of it。

 when you build an RBF network using modern way of training it。

 it allows you to deal with many batches。 So the number of parameters they don't have to be。

In a strong correspondence with the data points you use。

So you can play with different sizes of networks and see how it goes， where those networks are。

 the training is usually they train the centers of the basis functions first。

 and then you train the weights。 and then you iterate over that。

 So it's possible to use that more general framework to solve this problem。

 It's a modern way of doing that。 Well it's not going to use Lisa squares。

 It's a gradient stochastic gradient descent solver。This is。Vising。The basis that you choose。

 this is a global solution， whereasas the other one will just do a search for you。

To find whatever that works。The reason we talking。Why do we need the sense。And plus one。

I make the whole matrix become undertermined。So that make the problem become not finding the least problem still like that。

 I still have another extra waiting for5 p0 as a1 I think that' make the problem become。



![](img/4b0d43562f19c84b95d59cff043c83c1_59.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_60.png)

Not quite the more foral。

![](img/4b0d43562f19c84b95d59cff043c83c1_62.png)

They's just finding what on home for。Half of the double squares。So I think that's a question to。

We expect， but what entire one is a little bit different than again we saw in this problem。

 does it make sense？I'm thinking about why， I don't teach 501。 What can you。

Explain what's the problem formulation that is different。If we have的。Over。

ToFind those best solutions。嗯哼。😊，Weve right。It's less than。Where find it。他的费用状。That's the point。

So you're asking the relationship between minimum norm solution and this problem So at least the squares problem is for overdetermined system if we're dealing with underdetermined system。

 we have to talk about。The minimum known problem。The minimum norm problem。

 This is a quadratic program you can use off the shelf quadratic programming solvers， such as。

OS S Q P。To solve this。Because quadratic program has quadratic objective function linear constraint。

However。This particular example。Has a closed form solution。Not general quadratic programming。

 but this particular problem， the minimum norm solution will be。Still。

 you will get the normal equations。But you are， you have to do fee， fee transport。

 So you have to get the。The other pseudo inverse of the function。Wt。

So the solution to the minimum norm problem instead of in general， we would write a equals Q R。

For the minimum， and then the solution will be。R back slash Q transpose B right for A X equals B for the minimum norm problem using the same notation I used above。

We factorize a transs to be Q R。And the solution will be Q。Times。A transs back slash x。

So in this particular case， you can solve it， but that's sort of equivalent of what we're doing here。

We're using a different narrative here。 It's called regularization。

 And we have a parameter to play with the。Relationship between two objective functions。

 When you add the regularizer， then it's over the time again。Because we add rows。

The right hand side is 0。But we have role to say that， find the。Smallest weight， close to 0。

So these are just different methods we can solve the same problem。



![](img/4b0d43562f19c84b95d59cff043c83c1_64.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_65.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_66.png)

So that was just an example。 you see that。Even linearist squares is very powerful。 You can solve。

Really interesting problems。Oh， I was curious。With the。In the above slide。嗰啲。The matrix is very。你该走。

And for this。Maybe。Question is， would any matrix lemma help with inversion time efficiency。I guess。

That's why people work on these things。The second problem。

That is our main goal to learn how to solve it is nonlinear least the squares problem。

So in this case。We are no longer dealing with a residual。That has the form of A X minus B。

Whereas the residual is a nonlinear function of x。So it can be anything that does not have this form。

However， if you still minimize the norm of the residual。In the same fashion we did。

 the objective function still defines at leasta square problem。 in this case， it is nonlinear。

So the residual is a vector valued function that takes an n vector and gives you an M vector。

We assume it's a smooth。It's not necessarily。AI。And if it is， then in one step。

 we will recover the solution because it reduces to the linear case。

So the norm is squared of the residual corresponds to the sum of squares。

Of individual entries of the residual。 So each of the entries itself is， of course。

 a nonlinear function。That takes the entire input and gives you a single real number， right。So， R。

Is a vector。However each of them takes the entire input。

Which is an n vector and gives you a real number。In general， right， the special cases， it might not。

If we write the Taylor expansion of。One entry of the residual vector that gives the familiar Taylor expansion of。

The scalar function。Sorry， it's not the scalar function。 It's a single output function。

 So we get the gradient transpose。If we stack them into。A vector。

By stacking these gradients as row vectors， we get a Jacobkuan matrix。Right。

But you could do change a variable again and。Write it in form of D a Delta step。



![](img/4b0d43562f19c84b95d59cff043c83c1_68.png)

So， the Jacobkuan is。Stack。Version of the gradient for a function that has。Multiple outputs。

When the function takes a vector and gives you one real number， you can talk about the gradient。

When you have multiple outputs， then we have to talk about the Jacobuban because the mapping is from input to a vector。

 not just one number。So each row is your familiar。Graient。

Partial derivatives of are one with respect to all the inputs。



![](img/4b0d43562f19c84b95d59cff043c83c1_70.png)

The Gauss knew an algorithm。

![](img/4b0d43562f19c84b95d59cff043c83c1_72.png)

Is a method for solving the nonlinear least squares problem and the algorithm。

Starts with an initial guess。 unlike the linear case， No nonlinear problems required。

They require an initial guess。Because these are local solvers。

 so we need a starting point and then continue the search from that point。So， for。

Some number of iterations。Continue until convergence。In general。

 there is no guarantee of convergence。So that。Starting from an initial guess。

 we linearized the residual。So we will have to calculate the Jacoban。

 right once we know the Jacobkuan， of course， we know the linearization。

Then solve a linear least square solve problem at that it。Because the linear rise form now。

 this is an a form。So we just need to solve the。Normal equation。To find the step size。

And then we update this state and continue。Now， you might say why there is a negative sign。Previous。

 there wasn't。 Well， because we linearized， there's a sum here， right。

When you apply the first order and necessary condition， you have to move something to the other side。

 it gets a negative sign。But as peer previously。We wrote A X minus B。 when it goes to the other side。

 it gets the positive sign。That's why it's like this。



![](img/4b0d43562f19c84b95d59cff043c83c1_74.png)

So， the Newton method。Uses gradient and Hasian。So to apply the new term method。

 which is the second order method。We come up with a quadratic approximation of。

Our objective function around the current gas。So the model M will give us a local quadratic approximation of the function。

Then we apply the necessary condition for。This approximate model， which leads to。Solving。

This linear system of equation。SCN times。The deelta。

Of the variable that we want to solve equals negative of the gradient。If the hessian is well defined。

 we can invert it or factorize it。We get the step size， and then we update it。

So this is different from Gauss Neton， and we'll point out in the next slide why。

For the new term method。In general， there is no preference for low minima or maxima。

 It will just find the stationary point。And it's very fast near the solution。

 you had quadratic convergence。There's no preference， because， depending on the。

Definiteness of the Hessian。 you might be dealing with a maximum or。Mimal。



![](img/4b0d43562f19c84b95d59cff043c83c1_76.png)

So what's the difference？So you can use both of them to solve this problem。So， the difference is。

Can become obvious when we look into it this way。The gradient。Of。

The nine nonlinear is a squares problem。Gradian， the objective， the gradient。

Is Jacobian transpo tie the residual。This is one half。Our transs。R。So the gradient of F。Which is。

Partial derivative of f with respect to all the acts。Is。Of course。

Partial derivative of the residual with respect to x times。The residual plus。One half。

Of our trans codes。But to keep it consistent， I we need to transfer this。 So this will lead to。

And Jacobkuian is partial derivative of the residual with respect to X。

 This leads to Jacobubban transpose R。So the gradient of the objective function overall as some of the squares of the residual is Jacobubbian transpose times the residual。

The Hesan。Is the gradient of。Is the Jacobian of the gradient。So， if we take。

The derivative of this term， now you have the same way we follow the light in its rule that。

First derivative with time， Y plus。First one times。The second derivative。 So the first term。

 when you take the derivative of R， it gives you Jacobubbian transpose times Jacobubian。

 the second one， that's where the second order derivative will show up because we have to take the derivative of the Jacobubbian matrix。

Whatever it is， that will show you some second order derivatives， and let's call it S matrix。

So the hessian actually can be decomposed into Jacobkuian transpose times Jacobkuian plus some S matrix。



![](img/4b0d43562f19c84b95d59cff043c83c1_78.png)

So in Gas in Newton Reeration。

![](img/4b0d43562f19c84b95d59cff043c83c1_80.png)

Where we have Hen times D equals negative of Jacobubbn translus R。

StN is Jacobian transpose times Jacobian plus S。 in Ga's newton。

 we do not calculate the second order derivative。We just approximate the Hasian using Jacobkkuvian transfers times Jacobkkuvian。

Which is arguably much simpler， we don't have to calculate the second order derivative。

We still benefit from second order， like Salr。Result。Which makes it very attractive。

So Jacoban transpo， Jacoban。Is an approximation of the Hassian。And it's a good approximation because。

It's always positive semi defite， whereas S in general， can make the Hessian none。PSD。

There is no guarantee that you do the exact calculation。And your HaN is positive definite。

So if the residual is a small， you can expect similar behavior from both methods。And。

We use Gauss Newton。We don't use hesian。So we don't need to calculate the second order derivatives。

This kind of。收ber。Yes。I results。The question is， is this related to the notion of local solvers and initial guess。

 no， both of them are local solvers。We're just comparing。Two methods， Newton and Gaus Newton。

Nurton uses the Hassian。The exact second order。Terative。Gus neoone is a technique。

That is specifically for the least nonlinear least squares problem。

And it approximates the Hessian using Jacobuban transportpose times Jacobkuian。So goes Newton。

 you can't apply to any problem。 it needs to be a least squares problem。Newton is more general。

Is there any concern of those smoke because we're taking？Is there any consent of over approximating。

 what does it mean？还是。Creating an approximation of the second。待会。You might get。

We direct results of that approximation。It's possible not getting the correct answer。

You can't fix it。So you have to go back in tune and check what's the problem。 So generally。

 if the problem is well behaved and。The last residual that you define。

Satisfies the assumption that it continues， and。Smooth， then starting from an initial guest。

 you will find the local solution。 Now， whether that local solution satisfies your need。

That's a different story in Islam， when we find a trajectory and that trajectory should help us to reconstruct the scene。

 the local solution might mean。That the walls are intersecting， and the map is inconsistent。

 Obviously， that's not good， even though。Mathematically wrote that's a solution。

But doesn't satisfy our need。 We need a mean local minimum。

That is sufficiently close to the correct reconstruction and trajectory。

 And that's the challenge in Islam。That leads to current effort in finding global solves for Islam。

 There are some progress， which generally speaking， is difficult。

To have the global solver and have it fast online， you can solve it， but it will be probably offline。



![](img/4b0d43562f19c84b95d59cff043c83c1_82.png)

So that's an ongoing research topic。

![](img/4b0d43562f19c84b95d59cff043c83c1_84.png)

So let's make the target tracking problem， just a warm up example。 Now linear。

 the motion model is the same。 The measurement model index in this case is。It's rangeing。Bearing。

So if I'm going to estimate 2 d position with range and bearing， the range is the length of that。

Relative measurement and archrc 2 will give me。The relative angle with respect to the vertical axis in this case。

The Jacobubian。Of the measurement model can be calculated in closed form。

And the Jacoban of the measure model is， of course， trivial because it's linear。

So we can stack again。There least a squares problem。



![](img/4b0d43562f19c84b95d59cff043c83c1_86.png)

However， when you do it this time。The problem is。This Jacobban matrix， that。We build。B。嗯。Thanks。

So this linearized system， it will change every time we update the guess。

So although you can linearize。We need to evaluate。A。来ft。

And side matrix and right and side add the current guess， solve the system， take a step。

And reevaluate them again。 So at every duration， we have to reevaluate this linear system and solve it until convergence。

 Some conditions are met。Generally， this is the recipe。Later in the slam。

 we will see that we like to reuse previous calculations as much as possible。

Because we have to solve everything from scratch every time。It's never going to be online。



![](img/4b0d43562f19c84b95d59cff043c83c1_88.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_89.png)

So in a similar fashion， you can construct your residual， calculate the Jacobhubian。

So all you need to do form as a residual， evaluate your Jacobubian。

The rest is what you see in the algorithm。Once you know the Jacobubian。

 you can solve the Gaus Newton。

![](img/4b0d43562f19c84b95d59cff043c83c1_91.png)

So off the shelf solvers want the residual and Jacobkuan usually from you。

Then they will solve the list squares problem for you。



![](img/4b0d43562f19c84b95d59cff043c83c1_93.png)

So in this case， the initial guess。We have from range and bearing is very noisy， the green line。

And the Gaus's near tone will smooth it and give you。The gray or black line。 Now。

 we are fortunate enough that we can use the measurements to actually get a guess of the solution。

Sometimes that's even not possible because imagine we only had bearing measurements。

But we have it from different angles that we can triangle it。

It's not that easy to come up with an initial guess。You might need to。

Try a couple of initial guests or do other tricks to initialize the problem。Right。



![](img/4b0d43562f19c84b95d59cff043c83c1_95.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_96.png)

Okay so。You learn the Gauss neton。 Now， if you see an a linear cause problem。

 you know how to solve it。And there are many good off shelf solvers。

 one famous one that is also supported by Google It is series。And in G2O Library。

 which is a slam backend。It uses C solver。In most of them。Programming packages like Math Lab。

Languages like Julia and Python， you do usually have a solver for these problems。Okay。

Now you will use another library called GTSM。That's in your。Onwork。7。

You will learn how to work with the API of of the library that will be very useful for your future。

Adventures in Islam。So now we're going to talk about。Globalization strategies。

 globalization strategies are strategies。4。Global convergence to local minimum。

It's a very popular topic in Europe。You hear about it a lot。So。In the same。Line up thinking。

 we would like to have a set of strategies。That。And enforces global convergence to a local minimum。

 doesn't have to be the best solution。 And at least you can find the minimum。Local minimum。

For the problem。And that really corresponds to。One。

 one very popular way is to the damped version of the algorithms。Which says that。

 don't take the full step。And calculate step size。 And this is step size， depending on the problem。

 can be very critical。 There are a lot of problems that if you just ignore this as step size。

 there is no convergence。Whereas if you calculate the step size carefully， you get nice conversions。

So it can be very important。 One nice thing about using libraries for solving your problem is that this is usually handled internally。

 If you do it yourself。😊，you ignore this。For particular problems， your solver might work。

 but in general。It won't be applicable to all problems。So we want to find the step size。

 the condition is。That。Direction of D is a de direction。

That means that the objective function needs to。Be reduced when we take it step。In other words。

 if you take the directional derivative of the objective function along D。Using this alpha value。As。

The step size of moving along that direction。From calculus， we know that that will lead to。

The gradient transpose times D。 is the projection of your gradient along that direction that you want to move。

That's the dot product， It's the differential directional agg is the differential of your function。

Howlong the direction you want to move。Not the standard basis of， for example， R N。

And that means gradient transpose times d。Which is a dot product of gradient and the direction you want to move。

So because of that， d is a decent direction。And if your're Delta F。Right， is less than0 or。

The dark product of the U gradientian with the direction you want to move is negative。

Then you call D at theent direction。So， for。For direction D。

The newton direction is a descend direction。 if your， if your hessian is。Positive definite。

That means the carvature is positive。If it's not， you're not going into a valley。For gas neton。

If the Jacobubian is full column rank， it's not singular。

 that will give you a decent direction because Jacobkuban transports Jacobkuan is guaranteed to be positive semi deffinite。

You might get zero eigenvalue if the columns are linearly dependent。Other than that。

 it will be a decent direction， which makes it。Nicer for you。

So the goal is to solve a one dimensional problem， right？I' cut step。Given it the same direction。

Solve one dimensional optimization problem， such that。

This alpha will minimize your objective function。 That's the idea。

 So you can exactly solve this optimization problem that that is called exact line search。

Because inside this is a line， right？With different values of the alpha。

 as if you're moving along a line。So it's called line search and you get exact line search。However。

 in practice， we do not do exact line search。Because it can be expensive。But also。

 there is no guarantee that the exact line search works better than some heuristics and approximations。

The inexact line search is called backtracking。 This is one popular algorithm。

Which uses Army Ho gold to stay in condition， which is this condition we have here。That。

The differential of your function， directional derivative of your function。

You want this to be negative。So what you can do， you can。Use this condition。And pick。

You find this like this， right？You want this to。第一。Negative。Right， so this is the condition。

 So the idea is that pick a large alpha value。And backtrack with some factor， 0。9。

 whatever you choose。Reduce it until you find the good。Alpha Valley， right， that's the idea。さい。

With theSo why't it。对。What if that being the opposite of what you want？Wouldn't that make it more？

Easy to get stuck。は大います。Would' the question is，Would' an the damped version of the algorithm make it easier to get the stock in saddle point and local minimum？

hy。Wohy， that's obvious that makes it easier。Well， we have well， I guess visit a you know here。

More slowly。第。AndP these。可以。So the only downside here is that we're moving it slower。

 it can delay the convergence。There's no harm in moving is slower。If you're patient。

But we want to take the maximum step size that we can。Obviously， instead of iterating 100 times。

 it's nice if you can iterate five times。That will be。Preferred。

So the damped version of the algorithm can increase the number of iterations。



![](img/4b0d43562f19c84b95d59cff043c83c1_98.png)

Which leads to your question， leads to。

![](img/4b0d43562f19c84b95d59cff043c83c1_100.png)

The next is strategy for globalization， and it's called trust region methods。

I think this will answer your question。No， I I guess。There's also。我俾证。

We're not talking about momentum at all， so we don't want to bring it into that picture。

We can talk about it offline。It's not related to this discussion。Does that make sense？

We'll be out of time。Yeah。道。We do。So the question is。

 why not choosing the negative of the gradient to be a decent direction， We do。 And that is。

One choice in gradient descent。被告人民规。Reside。下。You。我们三。た。You wouldn't have to check please the next。

know。The gradient is not the only choice， in general， you can move along any direction in this space。

The negative of the gradient is a decent direction。

And it is the fastest way of moving to a lower level sets of the function。But again。

 that doesn't mean it's the best direction， because。

It is a known behavior of gradient descent that it will zigzag to reach the solution。

 and that's very undesirable because it takes so many it， whereas you use conjugate gradient。

It's a different approach， it will change the direction。Based on some techniques。Dity。

 do all direction of the gradient。It will converge。 It's guaranteed to converge in。Any iteration。

 if you have。And dimensions。So that shows that the gradient ands is the best direction to move。

 It is the obvious descent direction。But in general， you're free to move even randomly， right？

We're talking about。Is this something that we do or these two steps go line search or these things that we do in each iteration。

 so each iteration we figure out what the best right in each iteration you need to find the best step size because at each iteration we calculate the new gradient。

And Jacobku and so we want to know how far we should move。

Now you're not going to do it here in our problems by hand。

 but generally it's good to know that inside the solver， something like this is happening。

Whereas when you implemented a Gauss Newton simply yourself， you might not calculate this。Right。

And if you。You know， code it yourself and you see that when I multiply my steps each update by a factor 0。

2， it's working， but when I'm not doing it， it's not working， then you know it's because。

Your steps are too large now the reason。Taking larger steps will。

Not guarantee that the objective function will be reduced， minimized。Because we are working。

 remember， we're working with a local approximation of the function， we linearize。Now。

 how far dead linearization or quadratic approximation is valid， that's the question。

Maybe if your function is。Actually， quadratic， then it's valid， obviously everywhere， right。

 And the linearization is fairly valid for a good portion of your function。So how far your model。

 which is not exactly your objective function is valid？When you linearize it at the current step。

Well determine that the reason in general there is no answer for that because well。

 we have to talk about specific objective function or class of function and their behavior。

SoWhi makes it very difficult to come up with。General rules， one idea to address this problem。

At the cost of making your solver slower is called trust region methods。Trust region methods。

They try to。Pick its step size deelta。And condition your。Local。

Minimization problem using linear systems or quadratic approximation of your function。

 using a constraint that you cannot move beyond this deelta region。

How much you want to trust your model。Using this Delta region that you have to pick as a distance。

So we can quantify and reevaluate our trust and the model。By calculating the actual reduction。

Of your function before and after taking a step， divided by。

Expected reduction using the approximate model， linear or quadratic。Now。

 if this is below a threshold。😊，We should reject。That。Delta movement here。

 D includes the subside that you want to move。 It's the direction and the length that you want to move。

Below， because if your're。Delta and your。Function is。Small， but the model is large。Right。

There's a discrepancy between your approximation and。Your actual function。

 So you don't want that you want this ratio to be close to each other。The closer they are。

 the better。So， if this is。You pick some threshold oil。 General， they work like this。

You pick a deelta。 If you have to reject it， then you shrink Delta because。

You're at the region that you do not trust your function approximation。

 And then you keep doing that until。Slowly， you can move to a better region， hopefully。

So this is a main idea behind trust region。 of course， there is much more。



![](img/4b0d43562f19c84b95d59cff043c83c1_102.png)

Into the actual algorithms。And the way it is that maybe you start from a large delta， right？

If you're here， you would pick a large step。But。Using that quantification。

 maybe that's not a good idea because there's a discrepancy between the approximation and the model。

 then you have to reduce the delta and then maybe take a smaller step。Maybe again。

 you take a smaller step。Until you have maybe a minimum。Step size that is safe to take。



![](img/4b0d43562f19c84b95d59cff043c83c1_104.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_105.png)

So the gal's newton is good。 but the problem is。In practice， we might have near singular。

Jakubian transs， Jacobkubian depending on the problem。

 or sometimes you have you want to have some notion of trust region in a soft way applied to your problem。

 Len big Markqu algorithm will do that for you。 So this is the generalization of Gausssonton。

An extension of that。When。Instead of just working with the。H the N or its approximation。

 you add a lambda I。Which you remember when we regularized the problem。

 this popped up in the solution。So larger trans region。

Neighborhood corresponds to small penalty factor， lambda。If lambda is0。

 basically there is no trust region。If lambda is。So if lambda， if Delta is large。

 that means you're free to move。If you're free to move， there is nothing to regularize。 So lambdas。

Very small or zero。If the region is small， that means you're not allowed to move too far。

 then lambda is large。You're anchoring the solver to don't go too far。

 You're regularizing it to stay where you are。 That's what you're doing。Similarly。

 there ideas to update Lambda and reduce it iteration。

 The original idea was that Lenbergck method was。Just add Lambda I， Marqut。Said that。

Less conditioned adaptively based on the diagonal of the Jacobkuan transport Jacobkuban。

 because as you get closer to the solution， we want to remove this。So you can converge faster。

 otherwise a regularizer might delay the convergence。

But typically we call all sort of variations of this Lenburg Marcot or LM instead of Ga Newton。

So I'm kind of confused about the penalty factor that we。We have a smaller delta。

Taking those large steps。P foot。On top of the fact world， not taking very large steps。

 now we also have something to panel is whenever we take large steps。

 which already something that's not very likely to happen。So。askingSo the large trust region。

 So if you if you don't have the trust region constrained， right。It's the default algorithm。

 You can take a step that is very large。What if you regularize？Your problem。

That will not allow you to move that far， right。So。Having a very large trust region， as if。

To the extreme case that you don't have it at all means the lambda is 0。Right。And then the opposite。

 obviously， is that if you shrink Delta， that means Lada is large， you。

Forcing your algorithm to stay around where you are。That will be geometrically。

 that's the effect of it。

![](img/4b0d43562f19c84b95d59cff043c83c1_107.png)

Right， so another。

![](img/4b0d43562f19c84b95d59cff043c83c1_109.png)

For the Mark points。He said that essentially adding some of identity， adding the diagram。或者证明。

Essentially that way。Decreases as you get closer to the answer， did I understand that？

Because the gradient is0， that's a necessary condition。 at the solution， the gradient is 0。The Gr is。

Jacoban Transs are。It just related to that， right？The derivatives will vanish at the critical point。

 which is the solution。But it's an idea that we can come up with other ideas。



![](img/4b0d43562f19c84b95d59cff043c83c1_111.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_112.png)

Can also think about it。 that large lambda。Will lead to basically in the limit it will converge to gradient descent。

 It will cancel the effect of second order。 and small Lada is the Gaus Newton。 That's something。



![](img/4b0d43562f19c84b95d59cff043c83c1_114.png)

![](img/4b0d43562f19c84b95d59cff043c83c1_115.png)

You can think about it。Now， to solve the linear systems。Ultimately。

We have to solve a system of something like this。 A X equals B or A D equals B。 A is a。

Sysymmetric matrix， if we have Jacobubian transpose time， Jacobkuan or in Lenberg markcod。

 we have a matrix like this， whatever you choose， ultimately we have to solve a linear system。So。

 again， do not invert a。 That's the last thing you want to do。In fact。

 you should put it in your dating app file。First thing you want is that makes me laugh。

The second thing that doesn't invent matrices explicitly。



![](img/4b0d43562f19c84b95d59cff043c83c1_117.png)

So two methods that we use are Tlliski and QR。So Choleski， if you have a triangular system。

 it's very easy to solve。 you can use forward and backward substitution again。

 regardless of whether it's calciums to live in by Marco。The sub problem is linear。

This is this course problem， we're solving your linear systems。If a is L transpose L。

 call L transpose d Y。First solve for y using forward substitution。

 then recover D using back substitution。

![](img/4b0d43562f19c84b95d59cff043c83c1_119.png)

This is using Chollles ski factorization。

![](img/4b0d43562f19c84b95d59cff043c83c1_121.png)

The QR factorization。Or it's called sometimes economic QR， because。Q is n by n。

 but it doesn't give you all the zeros are a smaller matrix n by n。

Q is an orthoagonal matrix or normalmal matrix such that Q transluse Q will give you。

identitydent matrix of size N R is an upper triangular matrix。So if A D equals B， Q， R D equals B。

Q transpose Q R D equals Q transpose B。This is identity。And R d equals Q transpose B。So in fact。

 we just need to solve this system using back substitution。 So QR makes it very easy to。

Just call the back of the fusion routine。

![](img/4b0d43562f19c84b95d59cff043c83c1_123.png)

But what's the difference？So QR does not need， obviously to form the。Cdratic form， a transposese。

 you can directly work on the Jacobubian。Or if you stack the regularizer， it will take this form。

It'll make a taller。Tlieky。Works with a transpo a。Q， R gives you Q R for a。

QR has a better numerical stability。In practice then， Choleski。

So if you are concerned with numerical stability， use QR。But Q， R is slower than Cholesky。

 Cholesky is faster because it's。Exploiting the symmetric， positive。

 definite structure of a transpose A that will lead to less calculations。

By exploiting the symmetry of that matrix。A rule of thumb use QR， always use QR， you'll be okay。



![](img/4b0d43562f19c84b95d59cff043c83c1_125.png)

Unless somebody complains that， why this is so slow。



![](img/4b0d43562f19c84b95d59cff043c83c1_127.png)

So。All of this story， the s that。We will formulate。Will end up。Having a linear systems。

 we will face a linear system to solve。 and we know how to deal with it。

 And the initial problem that we formulate the slam problem。

 the graphic slam will be a nonlinear least square problem。

All bundlele adjustment and computer vision， all sort of variations of that formulation。

We will see how to use this structure。And the sparsity of the s to make it fast。So next time。

We have to continue this discussion， because， unfortunately。Our parameters for Islam evolve。

And the group。The rigid body transformation is an element of a league group。

 We cannot just use the Gaus Neotton or Lenberg markcod for the Euccclidean space for that problem。

So next time we try to。Basically， talk about how can we do least the squares problem in the Lee algebra。

 Once we learn that， then we can solve。The graph is land problem。So that's the reason we have to。

Go one level deeper。At least the squares problem。So that's it for today。Next， Tuesday。

 we'll talk about。

![](img/4b0d43562f19c84b95d59cff043c83c1_129.png)

Gl's near turn only group。