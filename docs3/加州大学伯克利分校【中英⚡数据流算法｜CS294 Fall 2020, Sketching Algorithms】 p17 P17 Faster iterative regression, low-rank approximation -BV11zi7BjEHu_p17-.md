# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p17 P17 Faster iterative regression, low-rank approximation -BV11zi7BjEHu_p17-

![](img/28a17ad56521c2e9c89a6d23c87434b2_0.png)

Okay， hello everyone， so reminder as proposals are due today。

 and then I'm going to release PSet2 shortly， which do which will be due not next week。

 but the week but I think the week after next week。嗯。Very good。

 so we're going to continue with sketching for linear algebra。嗯。And we talked already about。

Kind of two approaches to analyzing sketching。For least squares， both of them were sketch and solve。

 So the the algorithm actually didn't change。 The only thing that changed was the analysis。

 So one of the analyses we said， look if pie is is a subspace embedding。

 and that's the only thing we condition on。Then we yet something good for sketch and solve The other thing was we said okay。

 let's do the Char approach。Instead of conditioning on it being an epsilon subspace embedding。

 we'll only condition that being like a one quarter subspace embedding。

But also that it satisfies the approximate matrix multiplication property for a particular matrix product。

 if you remember， I think that matrix product was something like U transpose W。

Where U was an ortho basis for the column space of X。

And W was kind of the optimal residual like u of basically x times beta Ls minus y。

So U transpose W should be zero， but somewhere on our analysis。

 we ended up with something that looked like。P U transpose pi W。

So we wanted to argue that's close to that's close to U transpose W which is zero。

 and we did that by using the approximate matrix publication property， viewing as VW as a vector。

 but we viewed it as a matrix with one column okay。

So that let us get away with fewer rows in our sketch because we didn't need。

A subspace embedding with as good error。So today I want to talk about you a third approach。

For using sketching to solve least squares， and this is basically using sketching to find a good preconditioner and then feeding that into something like gradient descent or like some iterative solver for least squares。

And I put the references for for that and then we're going to talk about how you use sketching from lower approximation。

And just a little big sneak preview。We're going to see that actually this turns out to be。

Pretty much。Although， I mean， as we analyze it， we're going to see it pretty much uses reuses exactly the same kinds of things we've talked about for regression。

So let's do these in order。So I already preot a little bit。I don't you know。

 this is not a course on optimization， so you you can say more about gradient descent in general。

But you know all you have to know for today's lecture is， you know the setup is。

You want to minimize F of x， F is some function you're given。嗯。And you know。

 you start off with some initial guess for x for the optimal x star call that x0 and then you iteratively refine it by moving in the direction of the negative gradient that should that a should be an x sorry。

So given that you're currently at some point Xt。To get to Xt plus y。

 you just move a little bit in the negative direction， think of gamma as being some small number。

You move a little bit in the negative direction of the grading at the current point。And。

There are general analyses of gradient descent that say， you know， if you know something about。

You know， the lipschitzness， for example， of the gradient of F。

 or if you have some understanding of derivatives of F， you can provever convergence bounds。

On kind of how quickly your error decays as you iterate this process。

So we're not going to do that today， we're going to focus on in the general case。

 we're just going to focus on the very specific case of least squares。For us。

 we're trying to minimize x beta minus yl2 norm squared。

 so I'll just call that f of beta right and beta star， which is beta LS is the minimizer of this。

And the way we're going to do it is we're going to pick some initial beta zero somehow。

 actually the somehow we're going to get back to that in a second。When we do when we use sketching。

 there's going to be a very kind of natural way to use the initial beta zero。

And then if you calculate gradients and C。Here I put gamma in one， actually。

UmThe direction you want to move in is this direction that I wrote x transpose y minus x B and T。

Okay。😊，So。I want to analyze conversions of this。And。As you're going to see。

Something that is going to pop out into convergence analysis is going to say， look if X。

And X has very good condition number。Meaning， say like all of its all of its singular values。

 not just the top singular value， not just operating but all the singular values are like close to each other。

 So like the ratio between the largest and the small singular value small willll get fast convergence and then we'll see that well。

 okay， so X in general is just some input matrix。X might not have this property that the condition number is small。

 that all the singular values are close together。And what we'll see is that we can basically force X to have this condition by doing some preprocess with sketching。

Okay。So for now， let me pretend like x actually has this condition and let's try to analyze this and see what comes out。

Okay。So。Let's proceed。嗯。嗯。colorSo let's do analysis。She was doing analysis on the right hand of it。对。

So I'd like to understand。Let's say。X beta。黐。minus。Y L norm is squared？

And I'm going to write this as。I'm just going to add and subtract basically the optimal solution。

 So this is equal to x beta T。Minus x beta star， remember beta star is actually beta LS。

 is's just the optimal solution of least squares problem。Plus， x beta star。Minus y al norm squared。

And this is a trick that we've already seen before， these two vectors。

 this vector and this vector are orthogonal to each other。

 right because the first vector there is definitely in the column space of x。

And the second vector is orthogonal to the common space of x again。

 because the optimal beta star is the thing that kills the part of y。

 which is in the column space of x right so x beta star minus y is basically y perp。

 it's the part of y that it's the projection of y onto the orthogonal space。

 So these two things are orthogonal。So I can write that as。X beta star。Minus y L2 norm squared。诶。

Plus。X beta t。Minus x beta star。And again， this is up to it。That's the best you do。Okay。

 so now I want to analyze this thing。So now I'm going to use， I'm to let me call this actually。

 let's let's say this is actually x t plus one and this x t plus one。

So now I'm just going to write down what is beta t plus1。

 I'm just going to write down the update rule， which is over here。So this is equal to opt。Plus。

X times。Beta T， okay， plus x transpose。Y minus x beta T。Okay。Mus x star。Mine is Bay star。

So I just expanded what beta T plus1 is in terms of our update rule。And this thing is， you know。

 there's the op that's always there。Plus， and let is expand this out。X beta t。Plus。Xx transpose y。

minus。X x transpose x beta T。Minus x beta star。Okay。Now， I claim that。This part right here。Okay。Yes。

I mean， what is that？You mean， it's basically， it's the projection of why onto the column space of no sorry。

 that's not what I want to say。 So， so I just want to say one thing about this。

 which is the following。 I want to say that this is equal， actually to。X， X transpose。X beta star。

Okay。

![](img/28a17ad56521c2e9c89a6d23c87434b2_2.png)

🎼Now。小。

![](img/28a17ad56521c2e9c89a6d23c87434b2_4.png)

Okay。I should。 I should figure out how to。There should be a way to there was a way again to ignore calls。

 right， which was。The sleepy sign I think right or no that that's just do not disturb。

 you have to go into your notification settings and turn it off that way。Oh really okay， yeah。

 let's just hope that isn't coming back then。嗯。Notifications， so， I'll figure it out another time。

So what does the sleepy thing do again？The sleepy thing is do not disturb。

 so if your thing is if your iPad is locked， then it wont like it won't like gang or vibrate。

Okay I see。嗯。good anyway， I claim that these two things are equal Why is that because x beta。

 so remember I can decompose y as y per plus y parallel right where y parallel is the part that's in the column space of x。

And why purpose the part that's orthogonal？So the point is like if you look at x transpose y。

 that's equal to x transpose y perp plus x transpose y parallel。X transpose y purpose 0， because。

 again， that's X transpose is like basically taking the columns and dot product them and y。

 But if y or orthogonals in the column space and that's 0。 So x transpose y purpose 0。

 The only thing that survives there is x transpose y parallel。Meanwhile， what is X beta star？

X beta star is y parallel， right？The optimal beta star is the one such that x beta star is the part of y in the columns space of x。

So does that make sense， so these two things are actually equal。

X beta star and y have the same exact dot products。 X beta star is not equal to y。

 X beta star is equal to the projection of y under the columns space of x。 Therefore。

 dot products with the columns of x are the same for both。So then I can rewrite this thing as opt。

Plus。Okay。嗯。Let me write like this。X minus x x transpose X。 looks like a mouthful。Beta T。

Minus beta star。嗯。And now here's what I want to say。Let's focus our attention on just this part。对。

And let's write that。嗯。Let's write up here let's just write the SVD of x。

 So let's just say that x actually is equal to some U sigma v transpose。

 This is just for the analysis， right， we don't have we don't actually need to compute this SVD in the algorithm。

 The algorithm is just least squares。 This is just for the analysis。Okay， so。

So now let's try to understand what's going on here， so we have。嗯。U sigma V transpose minus。

U sigma V transpose。 V Sigma， U transpose， U sigma V transpose。Times that thing。Okay。

 V transpose V goes away， U transpose U goes away， this is just U sigma cubes v transpose。

So this is equal to。So listen again we want to look at again。TheAll this is the norm， right。

 so this is the square norm。All these are square noise。Okay， so this is now equal to。U times。

 let's write it as one minus。Or let's this Yeah，1 minus sigma squared。识物。V transpose。

And then this beta T minus beta star。Right you agree with that if you just expand this out。

 this is U of V transpose minus。Use Sigma cubed to be transpoposedse。

 which is exactly what what we said above it should be。Okay， and again。

This is equal to dropping the U。Because again， since U has orthonal columns。

 Ux is the same row of x for any x。And then I can do， I can just say， look。

 the norm of a matrix a times x is at most the operator norm of a times the norm of x。

 so this is at most the operator norm of identity minus sigma squared。

Times the norm of sigma v transpose times that beta t minus beta star。And again， putting in an A。

 putting in a U or removing a U doesn't change the number of anything， so let's put you back。

That doesn't changed nor of anything。And then this is just equal to x again。Okay。

 and the point is now。If all the singular values， if like if x is very well conditioned and let's say all the singular values of x are very close to one。

 they're all between， let's say three/ halves and one/ half。Or you know， or between 0。9。

 they're all between 09 and 1。1。Then identity minus sigma squared， I mean。

 that's just a diagonal matrix with one minus the square of all the singleig values in the diagonal。

AllAll those singular values we just said are very close to one。So this thing is very small， right。

 this thing I can say is at most， you know， a corridor or something。Does that make sense？

If all the single values of a are sufficiently close to one。Then I can make， then I。

 you know sufficient， then basically this operator norm。

 all the this is a diagonal matrix where all the diagonal entries are very close to zero。

So in particular， they're all at most a quarters something。嗯。Okay， so sorry great。

 I forgot why are all the things that belly is close to one。No， I'm saying like if we were。

 if we were in such a situation， oh， I see， if X were in such a situation， then we'd be happy。so。

So now if you look at what we basically have shown， we've shown。

 let me highlight two parts of our analyses。I want to look at this part。You see what I've。

What I've highlighted in the box up above。Compared with this part。At the end。What I've shown is that。

嗯。X beta T plus1。Minus x beta t minus x beta star。Eline norm squared。

Is at most a quarter times x beta t？Minus X beta star。That seems great。So kind of every iteration。

 this thing is kind of decaying exponentially。When we go from T to T plus1。

 it drops by a factor of a quarter。Which means that if we go kind of log one of epsilon iterations。

We're going to drive this distance down by a factor of epsilon。Does that make sense？Okay， now。

Now I want to talk about， okay， yeah， going back to your question。

 how do we know that all the singular values are close to one and we don't。

And that's what we're going to fix using sketching。Before we fix that。I want to say one thing。Okay。

 so basically I want to say that so therefore this is at most。This at most a。They say e， you know。

4 to the minus t。Times。X beta 0。Minus X beta store。So again。

 if you run this log winter uppsilon steps， that4 minus steel base of the epson。Okay。

 so now I want to address a couple things。 What is how we're going to pick beta0 is that somehow。

Okay。I'm the way I'm going to pick beta 0， I mean， you don't have to do this。

 but here's something you could do。You can just basically pick。Beta zero such that x beta  zero。

Minus y L2 norm squared。Is that most 1。1 times optt？How do you do that。

 We already know how to do that you discussion solve。

You sketch and solve with Epsilon being a  tenth。Right the down I mean。

 one of the downsides of sketch and solve is that。Your kind of your complexities。

 your run times have this dependence on one over epsilon squared because you need or even， you know。

 if you do the Charlotte approach with AMM， one over Epsilon， but whatever。

 either way your dependence on Epsilon and sketch and solve is going to be poly one over epsilon。

So if you want really， really good error， you want like machine precision。Then， you know。

 Epsilon is going to be tiny， you don't want runtime that depend on one of Epsilon， it's terrible。😡。

But here， what I'm going to say is okay， just set uppsilon to be some constant like a temp。Okay。

 so this you can do with sketch and solve where now you know。

 your epsilon is a1t or it doesn't even have to be a tent， it could even be you know。

 a third or quote something。对。It doesn't really have to be that small at all。You just want thank you。

 you basically just want to make sure that this thing is at most o of in fact。

 even that would be I think enough。So that you can do discussion solved without paying too much in terms of your error parameter。

And then now。Now you can bound this thing down here。In the bottom right， I'm circling。

I'm circling in an orange。Yeah。Now you have that。嗯。X beta 0 minus x beta star。L2 norm。

 well then you can just use triangle inequality， this at most。X beta 0 minus y。pl。

X beta star minus y。So I've just added and subtracted Y， and then I did triangle inequality。

And this is at most you know 1。1 opt plus opt， so in other words， this is like at most 2。1 opt。

I guess I defined Op to be the square。 So this is like， oh， of， I guess。However Ruolt， let's say。

Which means that if you square it。That's almost all what。So was 2。1 out。Okay， so now that's great。

 you're really getting epsilon times off。Right， so。Epsilon times opt error。

In log one of our Epsilon iterations。So that's something if I really want very high precision。

 that's something that I think makes me happy， I like seeing log winterps line by runtime。

 it's as opposed to poly up line。Now， okay， now the only thing that's left is you say， well Glani。

know， back to the original question， why do I know that x has single values close to1 well the answer is that it doesn't。

But now here's what I do。I compute a subspace inttting。Okay。And I look at， say， pi X。

And pi x is equal to some u prime， I compute the SVD of pi X， but again on and pi。I's like I's say。

 a one third subspace embedding。So again， it's not an epsilon subspace embedding。

 even though I want epsilon error， it's a constant quality subspace embeing。

So it only needs to have D rows， O of D rows， or if I'm using account sketch， O of D squared rows。

 there's no dependence on epsilon here。Okay， and then I compute the SVD。

 that only takes me polyd time because this is a D by D matrix or d squared by D。

And that's equal to u prime sigma prime V prime transpose。嗯。

And now what I do is I define R and matrix r to be v prime sigma prime inverse。Okay。

And now what can you tell me about？诶。嗯。About the matrix XR。Okay。So。嗯。Well。We know that。For all X。嗯。

The norm of X。Is roughly equal as well it's equal to。The norm of。Let me let me call it sorry。

 let me call it X， let me call it Z。For all vectors Z， if you look at the norm of z。

 it's equal to the norm of pi X Rz。Why is this true？Right。It's true because pak R has， Yeah。

 go ahead。 Oh Yeah， I was gonna say p X R looks like it's just U prime， Yeah。

 which has it's exactly px R has orthoal columns so it preserves the norm of any preserves the norm of any vector。

But then now I use the fact that pi is a subspace embedding。Of constant quality。

Right so that means that the norm of z is equal to the norm of this。

 but that's approximately equal to up to one plus or minus a third up to like you know。

 one plus or minus a third。The norm of XRZ。Right because pi is a subspace embedding。

pi x times the vector has roughly the strain norm as x times that vector for any vector。

 in particular， the vector here is r times z。So now what we see is that。

XRZ has approximately the same norm as Z for all Z。😡。

That's exactly the statement that all the singular values。F XR are close to one。Meanwhile。

XR has the same exact column space as X。So solving the regression problem over x is equivalent to solving the regression problem over XR。

Right。Like what， you know？The optimum of the two optimization problems are exactly the same。😡，Okay。

 so everything that I just said。Just run it for XR。

Do the gradient descent steps with Xr instead of x。And then everything works out。

And also the nice thing is。You know， like what's the runtime of this？Basically， you need to apply R。

 so in every iteration， you need to apply right here。嗯。

You need to apply extra to stuff and you need to apply extra transpose to stuff。Now x is actually Xr。

But， you know。R is a smaller matrix， so you can apply R quickly and X， you know if you had something。

 if you were in a good situation like your original x was sparse。Great。

 you're still applying x each iteration and x is far so you can multiply by x quickly。😊。

So you can run， you can basically do each it in time that's proportional to the sparsity of x plus sum poly D term to apply R。

So overall， your runtime becomes something like。You know。

 number of not sparsity of x times log interpsson because log interruptson is the number of iterations。

Plus， some polyd times log by interrupts law。And then the polyd is there because there's a polyd cost up front to compute R to compute the SVB。

And then there's another polyd per iteration， it's like something like d squared to apply R。Okay。

 so any questions about anything on this slide？Around the board before we talk about the rank approximation。

Okay， so let's move into the rank approximation。OkaySo what is this problem， so given as input？

Is a matrix A。which again I think it was n d。But here， I mean。

 it's for the speed up we got for a regression， we assume that the matrix was lopsided so that n was something much bigger than D here it's not going to matter so much actually you can use sketching for faster work approximation even for square matrices。

And。We want to compute。Approximately computed， actually。The best。Ran K approximation。是 a。

Under some norm。And you know， we know we know， you。

 we decide ahead of time what norm we're interested in doing this in and also K is a parameter that's given up front。

There's a theorem。That。This is like the Ehart Young theorem。That the minimizer， the argument。Overall。

B of rank K。I'll say， a minus B。Is equal to。A K， which is which is equal to。要其。S what K Vk transpose。

I'll see what that means in a second。For any。Mationally invariant norm。For example， For Venus norm。

Or。L2 to L2 operator norm， you know the operator norm that we usually talk about。And what is UK。

 what are UK Sigma K and BK， remember we can write the SVD。A is equal to。

Use sigma V transpose where kind of。You is this matrix。Sigma is some matrix like this。

And then V is some other rate， so this is sigma。And then， V。And write just maybe consistent。

 So there's some of you here and then V is also some other matrix， which is。诶。So Sigma。

 what's the order of the dimensions of Sigmas as I've been talking about before。

 Sigma is like R by R where R is the rank。And then let's say A is N by D。

So then this would be n by the rank， and be this would be D by the rank。This is V。Yeah。

So what is UK Sigma K and again， you know I know that this is like this thing here。

So I guess it's what you might imagine， so UK means。UK means。I just basically take the first。

K columns here。And then sigma K means again， I only take the top the top K singular So again。

 I also have Sigma1 is gram equal to sigma  two is gram equal let it。

 sore they're like stored in descending order。So I only take the top。The top K singular values。

 that's in theK。And similarly here， I only take the first K。就。

Right and maybe another way to write the SVD to think about is。I that right， so。Yeah。

 I think you can also write。That's the same thing as basically the sum over I from1 to R。

If said my I， U I， V I transpose。嗯。Maybe those are the rows， everything like that。

I think that's right。The other think that's right。 So actually these if I should keep them consistent。

 these should be superscripts。Right。So equivalent， this is the SVD。

Where the UI are orthonormal and the VI are orthoormal。

 these are the columns of UN andV respectively and Ehart Young， Ehart Young says。

That the best rank K approximation is that you only sum the first K of them。对。This is the best kid。

the best to according into the Fibeius name。So forus Norm， L2L2 operator Norm， basically any norm。

That's avari to rotations。Okay， so。That already gives， you know。

 there are algorithms that compute the SVD， you know if A is n by D。

 they take time something like n times d squared。I think it's more like。

 I don't think you compute exactly you compute it up to precision Epsilon in the runtime something like n times D squared times log went Epsilon or something。

But the point is you know， it' it's like n times d squared where if n and D are big。

 you know that's a lot， and you can ask the question of whether you can go faster。对的。So。

 as we're going to see。So faster using sketching。嗯。We're not， you know。

 we're going to rather than compute， rather than compute。The full SVD。And trunccate。嗯。

What we'll do instead is。We'll compute some other approximate version and show that。It does okay。So。

我 computer cute。It tda， I'll call it。Which is not the actual optimal thing。

But it's equal to the projection。嗯。On to。A pi transport。 So okay。

 so I'll say what this means in a second。Okay， this is。So。The projection。The best。Ran k。Approxiation。

Of a。In the column space。Of a pi transpose。Okay， does that make sense。Okay。So what first of all。

 okay， so one question is like， why does this， what does Pi need to satisfy for this to work well？

Okay， so we have to analyze that and show why that that that suffices and the second thing is like why is this even better。

 like why is this even faster than computing the full SD。So here's what we can do。So speed。

 first let's address the speed because I think that's easier to deal with。

So if I want to do this exactly， if I want to compute aK to exactly， what I could do is， look。

 I can first do the following thing， I can say that A pi transpose is equal to u prime sigma prime V prime transpose。

And now what I like to do is。I'd like to。Look at the projection of a to the column space of api transpose and take the best rank K approximation so what I want is。

The projection of a onto the column space has U prime U prime transpose a。

And then I'm going to use this bracket K notation to mean I want the best right K approximation to that thing。

Yeah。嗯。Okay。And。What is this， remember， we already know that to get the best rank K approximation to some matrix。

 you compute it to SVD。And then you take， you know。

 you take you computer SD and then you truncate singular vectors in singular values， right？

So we already know that。Like。I mean， if you write the SVD of U prime U prime transpose A。

We already know what the first matrix in the SVD is， it's going to be U prime。So。

 you know I can write this as basically U prime。Times you prime。Transpose Ak。

Those two things are equal。And I can compute。Let's keep track of dimensions of all these things。嗯。

So A is an n by Z matrix。And then pi is mapping down to some dimension M。

Which means that the rank of U prime。嗯。The of U prime， the rank of Api transpose that most add。

Which means that this sigma prime here has dimension at most M。And this is A。那个是啥。Okay。

 which means that this U prime transpose now， the dimension here is at most M。And then this is Anne。

Okay。And then this is D here。So I can compute。In time。Or M N D。嗯。嗯。

And then now I need to take the best rank K approximation of this matrix。And for that。

 I need to compute， you know， one way to do it is to compute the SVD of U prime transpose A so I can compute the SVD。

Of U prime transpose a in time。Oh of。呃。Dm squared。Okay。So and then and then I， you know。

 I'm not going to multiply everything out of the end。

 I'm just going to output like the decomposition as my output。

So then I'm done basically I I can write you know so I can write now I can write down some kind of decomposition as like is equal to u prime times a product of some three matrices。

 so let's call it u double prime times some。Sigma double prime times some v vote prime transpose and like i'll just output this as my answer I'll just say that this is my this is my approximate rank K this is my approximate solution to the best rank K approximation of a okay this decomposition and I've done it in time M and D plus Dm squared and as we're going to see。

M is going to be something that's going to be like sort of like K。

So the bottleneck basically is this part。Where if you compare it to computing a full SVD。

 a full SVD would have taken time n times d squared。Instead。

 we're doing something like Nd times M where M is something like K or K over it's going to more like K over epsilon。

 so we've replaced 1 D with a K over epsilon。In fact， it's possible。

 maybe I'll add it to the lecture note， so I'm not going to do it now in front of you。😡。

It's possible to do a little bit even better where。You can replace both D's by ks。

 so getting an instead of getting an n times d times k。

 we get something that's more like n times k squared。And the trick there is to say。Look， you know。

 let me not compute。Because if you think about it like and let me not compute this。

 maybe maybe I'll write the following thing down。So you know what I want。Took to go faster。

What I really want is。To compute the argument。Or let me not call it， yeah argument over。

 let's say matrices is x。Of where the rank。Of x is at most K。

Of u prime x minus a for beingnous norm squared。And you can prove that， you know。

You can prove that if I solve this without the rank constraint。

Then I can just take a low rank approximation at the end and still do well， so can prove。

That if like， let's say x star is the opt。Without rank constraint。You can just return。X star。

 take the best rank K approximation of that。So instead， we can say， you know， look， we just want。

 we just want actually the argument。Of U prime x minus a for being a server squared。ok。

And you know what we did above is basically trying to solve this kind of minimization problem exactly。

To find the best thing in the calm space of you prime。But I claim that， you know， you shouldn't want。

 you know， if you want to go faster or don't solve this thing exactly。

 observe that it looks a lot like something we already know how to do。And what is that？Any。

It's not exactly something we saw， but it's very， very similar to something we saw。In least squares。

 Yeah， it's basically least squares， right， I mean， if you， you know， what is this， I mean。

 this is the same thing I was like。Column by column， let's call it， let's do this。

 So let's say you prime。X X is the I column minus AI。Ll two norm squared。

So it's basically like the sum of a bunch of regression problems， right？

Where were I'm sum over the columns of x or the columns of a。So。Instead what you can do is do。

Do a s solve or something， right and and get don't get it don't get the X that actually optimizes this。

But get an x， which approximately optimizes this。And do that faster using Ske and solve。And then。

 you know， that will give you an instead instead x star， you'll get some X Telta star。

 and then you return the best rank K approximation of that。Okay。

 so do we do that for each of the eye problems。No， dont even you don't even have to do that。

that will only come the fact that it looks like regression you just have to do in the analysis but。嗯。

I mean， I so so if you want to actually just solve this。

 the way you do it is so okay so what you're going to do is sketch and solve so maybe I should say this。

So let's say generalized regression。So now you have something that looks like。嗯。X beta or beta now。

 let me call it B for matrix， a matrix now。You want to minimize the Frbenian norm of xb minus y forbenian norm squared so you can imagine that each column of b is some beta and each column of capital y is some lowercase y which is a vector that we saw before so this looks this is like I see the sum I。

well， actually， let me just say this。So yeah， so basically the way to minimize this is。

To choose B so that X B is the projection of y， like column by column。Project each， you know。

 you want to project each column of y onto the column space of x。😡。

So say you want to minimize the answer。So what， you know。

 kind of the best thing you could do is make it so that every column of y is orthogonal to the column space of x。

 which you could just do using the same the same basic solution that you saw release squares so kind of beta star。

Maybe be something like。X，X pseudo inverse。X。Tranpose。Why I want to say。

So like sketch and saw will give you something like beta Tilda。Is something like pi X。

This would be ex buildings。嗯。Pi X transpose， pi X pseudo inverse， pi X transpose。

We're now wise matrix。I mean， yeah， it's basically the same thing as regression。

Does that make sense you't you don't have to solve it。

 you don't have to solve it like one column at a time。

 just you just do this and that gives you the solution to the little matrix problem。嗯。Okay good。

 so I think now that I just want to show is like the claim that。

This is actually even a good thing to do。Right。The claim that this。Is good。So claim。

If you define aK tilde。To be。The projection onto the column space of a pi transpose besttri K approximation in that column space of a。

It satisfies。嗯。A minus aka tilde for being norm squared。Is at most one plus epsilon。The actual art。

Which is if you actually took the vest rate of approximation。As long as you。

 now you need to say something about pie。So what's the thing that we're going to say about pi？

As long as。1。We， we need that pie。Pi is a one half subspace embedding。For some particular。

K dimensional subspace。And we'll see what that subspace is， it'll come out of the proof。And two。

PI gives approximate matrix multiplication guarantees with respect to Frbeous norm。With error。

You know， something like oh of squared enough of K。And maybe here I should put an epsilon to be safe。

嗯。So as long as Pa gives， you know。Let's imagine pi is being chosen from some oblivious distribution。

As long as for any K dimensional subspace， it's a one half subspace embedding with good probability and for any particular matrices you're trying to multiply。

With good probability， it gives you error root up slot over root k。

 then the claim is that this Atell la K is an almost optimal underforennious norm solution to low rank approximation。

So we're going to prove this claim， but before we prove the claim， we just want。

 I just want to understand like what。What does this mean in terms of the dimensions of pi？so。

Let's say that we have count sketch。So， one。It meansan that the number of rows has to be at least something like d squared。

And two means that the number of rows has to be at least not d squared K squared。

It has to be at least something like K of Repsstone。missy。

It's like whatever over epsilon squared where Epsilon is your error。

 but our error is root Epsilon over k， so it's k over Epsilon。

So this altogether implies that M has to be at least something like K squared。

As long as M is basically something like K squared plus K Repson， that's good enough。

Or another thing you do is like， let's say that is just a random random plus minus one matrix。

Then one means you just need M to be at least k oh of k。

And two means that you need it to be at least。Again， Ki Epsilon。

So that implies they can get away with M being something like Care Reon。

And we didn't talk about it in class。One way to go about it is to use a net argument together with fast jail。

 Another way is to directly analyze fast jail。In the context of somespace embeddings。

But you could do it with seba L2， you know， basically。Pie being something like。

Sampling matrix times hadam or 4ier times a diagonal matrix with size。嗯。

Then basically you can get away with M being something like。It's got to be something like cave。K。

 polylogue K or something K log K or Epsilon anything。好。

So this is what it gives you in terms of like kind of what sketch dimension you can get away with to solve this problem。

And again， remember now， this M matters because when I was talking about runtime。

 remember our runtime here had some dependence on M。

But M is basically going to be some K K rhpson or K squared。Okay。

 so what I want to do in the remaining time， and then I'll maybe have a little bit time to say a little bit about what's coming next week on Monday。

Is just prove the claim。Prove the claim that。As long this claim on the slide。

 as long as Pi satisfies these two things。Then。Projecting。

 finding the best rank camp approximation in the calm space of Api transpose is a good thing to do。

Any questions about this？Okay。他们是不起 kiss什。Okay good， so let's try and improve the claim。嗯嗯。Okay。So。

So we want to look at。So let me actually say following。Define。P to be the orthogonal projection。

Onto the call space。I8 pi transferpose。So what we're trying to understand is。

Right we said a minus ak tilde。嗯。Actuallyly。上次。Yeah， so let me actually do the following。

We're going to define P to B the actually orthogonal projection onto the calm space of。诶。

The following matrix。Which is the projection。On to the columns this thing basically。Okay。

So what we're looking at is this。Which I can write as。AK minus PAK for me is node squared。Plus。

A K bar， I'll call it minus P， A K bar。These room square。When I say ak bar ak bar。

 what I mean is ak bar is just defined to be。A minus a k。

Right so just maybe you're not used to seeing this， but。A fun fact is that。The Frbeius norm。

The Frbei norm squared of a matrix M。Let me go write that up top and red。

The Forbidian room squared of M。It's just the same thing as the trace of m transposing。Okay。So。😊。

I can write， you know， I can write。A is equal to aK plus ak bar。对。I can do that。嗯。😊。

And then if I look at the for me， and then I can expand this out here。As basically。8 k minus PK。Plus。

 let me me write it like this。Identity minus PAK。Plus， identity minus P。A K bar。

And then that's the producer square of that。And then by this identity up top for be norm squared is just the trace of m transpose m。

This is the trace of。This whole thing transpose times itself。And the point is。

If you look at you're going to have terms that look like ak bar transpose ak the cross terms and those cross terms are zero right because ak。

AK ak bar。Have orthogonal columns。Because again， remember， what is AK， you take the SVD of a。

And then aK is you keep AK is you keep only， let me maybe move here。Great。Right here。

 the SVD is equivalent to this thing。And AK means you only keep the first K。

An Ak bar means you keep the remaining things。AK bar is the main things。

And those two matrices have orthogonal column spaces。Because again， in the SVD。

 UN and V have ortho columns。So the basically， if you take the trace， you know， let's call this like。

诶 w plus 。You take the trace of。W plus Z transpose W plus Z traces a linear operator。

 So this is like the trace of W transpose W plus the trace of Z transpose Z。

 But then you have the cross terms plus the trace of。W transpose Z plus the trace of z transpose W。

 And the point is that these things are zero。Because the columns of W are orthogonal to the columns of Z。

Does that make sense？That don that's why I want to expand it。

 that's why I can write the Frmin storm square and I can decompose it as these two sums that don't interact with each other。

Okay。And then now what is this， this is equal to。Identity minus P ak bar for the norm squared。

Which is at most。Again， we had this identity before， another identity that I'll write above。Is that。

If you look at the Frbenius norm of Wz。It's at most the operator norm of w times thes。

Times the Frbidian norm of Z。What's the operator norm of identity minus P。

 well identity minus P is a projection matrix， it's a projection onto the orthogonal space to P so any projection matrix has operator at most one。

 you can't know projecting orthogonal projection can only decrease norm， it not increase norms。😡。

So this。It has herveni storm squared at most ak bar for beingia squared， which is just opt。Okay。

So the name of the game really is bounding this thing。We'd like to， we want this。

To be at most like some you know of up sometimes not。Okay。Okay， so let's bound this thing。

And as we're going to see， it turns out that this thing is very closely related to regression。嗯。Okay。

 so。嗯。嗯。We have that。AK minus PK could be a norm squared。Well。

 just expanding out what that projection thing is， that's equal to ak。Minus。

A transpose A transpose Api transpose pseudo universeverse。Times ak for being certain squared。

we projected onto the column space of api transpose。And then let me take transpos on。Both sides。

I meanI mean， transpo is the whole thing。This equal to。AK transpose actually you ready。

 like let me also。Do this way。And。Yeah， so little say transpo is aK transpose minus ak transpose。

And then I'll write here pi a transpose pseudo inverse。Pi a transpose。And let me just you know。

 take the negative on the inside that doesn't change the viemia form that's equal to Ak transpose。

Pi a transpose pseudo inverse pi。嗯嗯。诶。Transpose for theation experience。And again。

 if I sum them over columns。I'm missing a minus sign。Oh， minus ak transmit。So only sum of column。

 this is sum of all I。Of。AK transpose。Pi a transpose pseudo inverse， pi a transpo。

I've column minus aK transpose I've column L2 arm squared。Okay。

 so I know this looks a little bit like a mouthful。

Now let me rewrite the last thing on the next whiteboard。So what I said is that。嗯。

AK minus PK for being term squared is at most the sum over I。Of AK transpose I column。Minus actually。

 you know， that's what I dont want to see。AK transpose。

 and then I've had something like pi a transpose pseudo inverse pi a transpose Ithe column。マナ。

A K transpose if column， Uum squared。Okay。So I claim that this looks。Very similar to。

 it's not exactly the same as， but I claim that it's very similar to。Again。

 something that we've already seen。Does it ring any bells for anyone？Imagine。Imagine for a second。

 this is not what we have， but imagine for a second that。This was actually。

Imagine that this was actually。A transpose I。Now does it look like anything？Okay。

Maybe it just looks like too much of a mouthful that everyone got scared。

Or maybe people are actually their videos off working on their project proposals。But。Basically。

 what I wanted to say was if it had been a transpose I。

 this is exactly the error from sketch and solve regression。

imaginary your regression problem that looked like as follows。Imagine。Men or X of something like。

AK transpose x minus a transpose I。Alitude norm squared。你。ThisThis is a regression problem。

A transpose I is is a vector， Aka transpose is a matrix。

 find the vector x which minimizes the L norm squared。Using sketchch and solve。

We have we would find some extiilda。Which is the minimizer。Of the pi version。

 pi aK transpose x minus pi a transpose I。Which you know there's a closed form solution for what the minimizer is。

It's the project。 It's the。Basically you want， again， you want X to be such that。

Pi aK transpose X is equal to the orthogonal projection of pay pi a transpose I onto the column space of pi aK transpose。

 Okay， so I know that。Sounded very annoying to say， but this is just exactly equal to。诶派。

I guess this should have been a pi AK transpose。🤧咳。PoAK transpose pseudo inverse。嗯。派。A transpose I。

Okay。So I guess I should have said that。It's not exactly the same。

 It's the same if that thing had been a transpose eye， as well as。嗯。

This thing had also been an AK here， then it would have been exactly the same as a regression problem。

Okay。So it's not exactly the same， but now what we can do is we can basically try to use our analysis from last time of I guess our lecture on Monday。

Which did the following thing。诶。Okay。So。Just， I know。 this is。

A lot of there's a lot of this is pretty calculation heavy but。

All I wanted to say is you can basically use some of the tools from Charlo's。

AM style analysis of Ske So and plug them into our current situation。So in particular。

 if you look at the definition of gamma here， so what was the because let me copy over some of this stuff to our situation。

So that accident throw something away。So the Charlotte idea is。analyze questions song。

He made a few definitions。 One is that like now it's a matrix。 but' say W is the residual。Matrix。

From。出成。The optimal。Solution to regression。And then also。

There was also this thing where you defined you。Alpha your gam， I think。Was defined to be。e times。呃。

X Tilde star， which is the sketch solve solution minus x star。And if you remember。

 we said something like。Last time。We said something like。ja啊。Well。

 here here now gamma is going to be a matrix。 So let's say that's let's say that was a vector。

 we said last time gamma L2 norm squared was at most。

 And there's like a one half here or something was at most。Pu transpose， Pau。Gammma al squared。

 which we said was equal to。Pi U transpose pi W。Eoon norm squared， which we argued was at most。

Some like Epsilon Prime。Times the formin and review。Times the norm of W。

Which is just root out if it's a squared， I guess this is all squared。So this is opt。And this was D。

嗯嗯。Okay。诶。So we'd like to do that kind of thing here where we can now。Basically relate this。

To things that look like the norm square of some gamma eyes。And then。

And then basically we want to sum up the square norms of the gamma eyes。

We're going to do exactly the same this chain of inequalities and get something on the right hand side where instead of the matrix u it's going to be some it's going to be some matrix which depends on。

Which is not U， but something like UK or maybe VK and it's going to have ministorm squared k。

 and then we're going to be able to leverage approximate matrix multiplication with error parameter root up slot over k instead of root up slot over D。

嗯。so诶。I want to just， I think I just give myself something and I think I confuse myself on one calculation。

嗯。Okay， I'm going to fix this in the notes， but I think I should have ended with this thing here。

应我奇 much。嗯。Let me go with that being K and then I'll fix it in the notes。So when I was okay， so good。

 So now what we have is I said something like。We have。We have the sum of our eye。Of。That term。

 which is aK transpose。Pi A K transpose pseudo inverse， pi a transpose。嗯嗯嗯。I minus。A transfer在。

And I'm comparing this to the regression problem I said。M over x。

Of AK transpose x minus a transpose I。行。Okay， so if I looked at the term。Look at。AK transpose。

X tilde minus x star。Where this is the true opt。And this is the solution to catch and solve。Okay。

 so what is aK， you know， what is？What is the true optimal solution to this problem？

The true optimal solution is。Basically， you want to make so pretendant you know。You want。To project。

A transpose onto the column space of AK transpose with as little error as possible。And another。

 you know， so you get rid the transposes， you want to project a。

Onto the row space of AK as best as possible。And the best way to do that is just to simply choose AK。

OkaySo so your projection， you're going to project onto VK。So the true optimal solution。Has。

AK transpose。X star equal to。嗯。AK transpose I。Right so。Project。翻 to。Ba B。Where V is the row face。嗯。

The columns of V form a basis for the row space of A。So and then we already know what this is。

 the solution to sketch and solve is exactly what we had above。 This is going to be。Pi aK transpose。

 pseudo inverse。Pi a transpose I。Which is exactly the same。As this。Okay。So this is exactly equal to。

The sum of her eye。Of。嗯。Kind of。I'll call it aK。Transpose。X tilde I。Minus X star I。Ll2 norm squared。

And then by definition of gamma， right？GAamma from our previous analysis of sketch and solve using AMM is exactly this difference of。

A times the optimal， a times the sketch and solve solution versus the optimal solution。

 So this is equal to。The sum over I of basically u times gamma I。L2 norm squared。

 which is equal to the sum over I of。Gmma I L2 over squared。Okay。And then the solution。

 the analysis is exactly the same as last time， some of her eye gamma。I L2 norm squared。

Is at most so now we use the fact that we have a subspace embedding for the row space of Vk or for the call space of VK。

 So this is at most let's say one half times。Pi Vk transpose。排 v k。Gmma I L2 squared。

The sum of her eye， which is the same thing as treating gamma as a matrix now。Pi Vk transpose。排别成家啦。

For being more squared。Right， and then now what we say is that。嗯。This thing is equal to。

Pi VK transpose pi， and then we replace。This。Not this。 replace。He。You basically say that。VK。

 Im sorry。系咁呢排基都四时区。so we've put a W here。没。So the claim is that this thing。In this thing。嗯。

Have the same projection。Onto the calm space of pi VK transpose。

And that's exactly what we saw before with the AMM analysis with Charos， which I'll go to right now。

This。Right。So that's exactly the analog of this we said that。This thing。In this thing。

Have the same projection onto the column space of Pau。Okay。

And then you use approximate matrix multiplication to argue that。Well。

 this is just now this is equal to。I'll write it as pi VK transpose。Hi， W minus V K transpose W。

This is 0。But by AMM， this is ut most。嗯。Epsilon prime squared or Epsilon prime is your error times the Frbenius norm squared of VK。

Times the3 square squared W。This is opt。This is K。So if I set Epsilon prime to be something like root Epsilon overque。

This implies that this is at most absolutely times aren。Okay。

So I apologize that was a bit of a mess and I feel like I didn't。Deliver that as。Clearly。

 it's possible。But。I'll put it in the notes so you can review it and also I'll say that kind of maybe the punchline to take away from all of this is。

kind of you expand out what your error is， you look at the terms that you show up and you realize the terms that show up are basically identical to terms that showed up in the analysis of Charlo's。

Sketch and salt error for least squares regression when you depend on somespace embedding for a certain subspace as well as approximate matrix application。

So the only thing that changes here is like what is the subspace， the subspace is VK。

 it's the calling space of VK。嗯。And that's basically it。So。Yes， are there any questions？

Are there any I realized a road that took longer than I expectedancy so out of time？

ButAre there any questions about this？对。So everyone's gone。 So I guess I will see you all。嗯。

I will see you all on Monday。Good。

![](img/28a17ad56521c2e9c89a6d23c87434b2_6.png)