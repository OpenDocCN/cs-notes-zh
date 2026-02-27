# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p20 2024-10-28 - CIS 5650 GPU Programming Fall 2024 Guest Lecture 4.zh_en -BV1sRtresE67_p20-

But okay， that were good， I just had to hit the end。



![](img/1ce12f4ae7c2943f89de01fc24868ec4_1.png)

Yeah。I expect more people than meIt's all good。Ill wait matter minute or two。Oh。那应该该可。你真是你知啊。嗯。可以。嗯。

Okay。XX4。你你好怎么我现在直我打电话。This。啊，你不是。I。おすしょう。Okay hello everybody well Shaan's not here today so I'll be like facilitating I guess this is Liam this is the guest lecture I will introduce him and then he can give us lecture so Liam was a student in this class in 2018 his team was the first to work on a DxR project and we the first student team in academia to do so he interned in Nvidia and then he rejoined Penn for PhD with a focus on natural language processing he's interned and collaborated on research with Morgan McGire at Robblx and John Hopkins Johns Hkins。

And this is his fourth consecutive guest lecture in the class and' put a student favorite every year I can tell you I enjoyed this one quite a bit last time so it's good pay attention anyways with that I will hand it over right。

Thanks so much yeah I'm kind of surprised they keep inviting me back over and over again like at some point you know you got to got to spice it up but no it's great I actually really really enjoy talking to the students in this class because I feel like I don't know in a lot of the stuff I do research world。

 a lot of people are less concerned with the actual nuts and bolts implementation of the models and the acceleration and getting to talk to GPU students is great because they're like。

😊，But how does this relate to the you know to GPU bank conflicts warps you know and yeah happy to talk about machine learning so I'm going to give two lectures this week so this is the first of the two it's just the introduction to ML I basically have to get all of the introductory stuff out of the way so that we don't have to require you to have taken ML before I talk about the second lecture which is the really good stuff which is just how to optimize machine learning in KUudDa and then after those two lectures we've had many student groups attempt final projects with machine learning and a lot of them have been really successful we had like many pass tracer optimizations with like denoising with ML and then we had like image super scaling projects so yeah I'm really excited to see what you all do。

And yeah， with the introduction out of the way， first thing I always want to ask is how many people here have taken a machine learning class at all at Penn？

Wow， okay， the proportion of hands keeps going up year after year。

 The first time I asked this question， there was like one or two hands of。

 And now like half the class has this。 So this may be a lot of recap for the people who raise their hands out of curiosity。

 who's taken like 5，20 like the core machine learning class。 Okay， that's。

 that's a good amount for you guys like this will be all review。

 So feel free to feel free to like work on homework or something during this。😊，Cool all right。

 so just as a really quick intro I know I did you already introduced me but i'm a fourth year PhD student。

 I was an undergrad also here I did Comp and then submat for in Robo is anyone here in Robo or Comppi。

Yeah。嗯。And yeah， like you said， I took this class in 2018， surprisingly in the same room。

 never never changed from the same room， and I research primarily in generated content detection。

 so I do detect AI generated text and images， but I've also dabbled in doing like speech processing and then also just general large language model research。

Cool， so in this lecture we'll cover the absolute basics from zero so if you've never seen LL before like get ready because I'm going to basically give you like the entirety of 520 and like one three hour class so good luck with that and then also importantly we're going to talk about how do we know like what architectures to use。

 how do we improve the basics of machine learning and then also talk about potential tasks that we can apply machine learning to and that's to get you started thinking about what your final project is going to be。

Cool。So。A key part of this lecture is that we're not going to spend too much time talking about the theory or the math and my main goal is just to not intimidate you all like machine learning is actually pretty simple at its core。

 it's just when we get into a lot of this sort of stuff outside the core that it gets really intimidating but that being said we do have to cover a lot of ground so the lecture is going to be really fast please feel free to interrupt me with questions if you don't understand something and you really want to know。

All right。So starting off neural networks， I like to start off with a very basic example。

And that's with I would argue the first really useful applications of neural nets in an actual real world problem。

 which is handwritten digit recognition if you've taken an ML class you know how famous this project this problem is so our task is given a handwritten digit we want to classify what number it is so whether there's one two。

 three，4 five so on and so forth and our input is going to be a vector of length 784 with the pixel values is of zero to1 so if the letter is the number is。

Over one of the pixels， then it'll be one， and if it's not at zero and if it's sort of on the border。

 it would be some number between zero and1。

![](img/1ce12f4ae7c2943f89de01fc24868ec4_3.png)

So。Here's the neural network that solves the problem we take the 784 length vector and we put it。



![](img/1ce12f4ae7c2943f89de01fc24868ec4_5.png)

Into the input of the neural net。Like this？And then we have these connections and then the dots activate。

 and then ideally if we've trained it correctly， the dot corresponding to seven will activate at the output and we will classify the digit as a 7。

😊。

![](img/1ce12f4ae7c2943f89de01fc24868ec4_7.png)

Going back one slide， the final output is a K dimensional vector where K is the number of classes does anybody know what these lines are and what the dots represent？

你听到。Yeah， weights and。And notes yeah exactly right so each one of these circles is actually just a number and each one of these weights represents a weight which is just a multiplication operation。



![](img/1ce12f4ae7c2943f89de01fc24868ec4_9.png)

So when we put in our number， light the lid up dots are the ones that have like a high value。

 and then the weights are lit up when we multiply by a very large number。



![](img/1ce12f4ae7c2943f89de01fc24868ec4_11.png)

Okay改。So， for example。One set of weights you could see here， like two， three， negative 1， negative 0。

4。And these weight values are learned from data。Typically with machine learning。

 we just sort of hook up all of the weights and then we try to learn what the values of the weights should be from our data。

Does anyone know how many weights you would have for a given layer of input size N？

In this example on a right， it's fairly straightforward right， 784 weights。

 but if we had an output size K dimension。How many weights would we have in a layer？Yeah。

 simple n times k this gets more complicated， the more complicated we get with the architecture。

 but in the very basic case where you have everything connected to everything， it's always n times K。

😊。

![](img/1ce12f4ae7c2943f89de01fc24868ec4_13.png)

Cool， well， so unfortunately， there's a catch because we can't just do this forever。

 We can't just have。This over and over and over again。

 like how I had in this example and the reason being that。Linear algebra is。Linear。

So if you do these weights over and over and over again。

They all kind of collapse into one layer the way people usually talk about weights in a neural network is by looking at them as matrices so for example if we have an n by K layer。

 we have an n by K matrix we take an input vector and we're multiplying it by this n by matrix to get an output dimension k vector if you're doing that over and over and over again you guys know from your matrix transformations that multiplying a matrix a times b times C can just be written as one matrix so in fact all of the layers of the neural network collapse to one layer and that's bad because we don't get any extra sort of representational capacity and so in order to actually train a network that has multiple layers you need some sort of non nonlinear function in between the layers so that we don't have this sort of mode collapse and for now we'll be using the sigmoid function but I'll talk later in the lecture about why we may or may not want to use the sigmoid function as always the sigmoid function is basically just it's this function one over one plus e to the negative x but it basically takes。



![](img/1ce12f4ae7c2943f89de01fc24868ec4_15.png)

![](img/1ce12f4ae7c2943f89de01fc24868ec4_16.png)

Number from negative infinity to positive infinity and clamps it from zero to1。Okay。

So this is the full equation for a particular node or neuron sometimes so we have the。

Combination of weight times activation and then the sigma represents sigmoid so we do all of the addition and we put it through a sigmoid the final term is typically called the bias and。

I guess so。I'll ask you the question on the slide， which is what is the bias term doing here。

 why would it be good to have a bias term as part of this sum？嗯放多技ででた。

Don't relieve it when that particular weight is not very attention。 We have those。Yeah， exactly。

In the case where we have like a sum that sums to some very large number。

 or let's just say that because of the way that we initialized our weights。

 a lot of these sums are clustered in a very， very high area， so something like 100 or 200。

The sigmoid function really is only good for ranges roughly say negative two to two you know anything past that is basically just one or zero or something very close to that and so if you have。

Sums that sum to like 100 or 90 or something like that they're very very far on this side and therefore they're really hard to like there's no differentiating factor between a sum that's like 100 and some that's like 98 and so using the bias we can sort of shift where the zero point of the sigmoid is over to where the sort of mean of our layer is and that allows the model to learn。

The correct parameterization。

![](img/1ce12f4ae7c2943f89de01fc24868ec4_18.png)

Cool。Right so when we want to write a single equation for an entire neural network。

 not just any one neuron， we take our weighted sum and we convert it to a matrix equation so I talked about this earlier。

 but because we have n times k activations for a single layer we can just write that as a matrix so over here we have sigmoid which is element Y sigmoid and then this W which would be the matrix of all of the weights of the layer X which is the vector of our input and then B which is what？

Bs right cool I already mentioned this， the dimension of weights is n by k mentioned of x is n mentioned of B is k。

Or sorry， invention of B is what？Yeah， also end。And the dimension of output is okay， cool。

The learn parameters are just the weights and biases， obviously we can't learn the input。

Right and then if you're GPU programmer you should immediately think like wow。

 this is very very parazable you know you guys have spent a lot of time optimizing matrix multiplication and。

Machine learning is already looking like a very good GPU problem。

 but we'll talk about even more reasons why that's the case。Cool。



![](img/1ce12f4ae7c2943f89de01fc24868ec4_20.png)

All right。So to summarize。Neurural networks are basically just extremely highly parameterized。

 simple functions。 And it's just additions and multiplications with 13000 weights and 700 inputs。

 But it's nothing more complicated than that。 There's no crazy functional terms。

 The worst we have is like an E。😊。

![](img/1ce12f4ae7c2943f89de01fc24868ec4_22.png)

嗯。But。😡，The burning question is now， how do we actually learn what the correct value is for all of these weights and biases？



![](img/1ce12f4ae7c2943f89de01fc24868ec4_24.png)

So first I want to pose the hypothetical， which is to imagine we had some function that takes in the input and the weights and biases that told us for a given input how bad our neural network is。

 how good or bad， then the problem of learning the correct weights just kind of simplifies down to just trying to find a minimum of this function。

 so the set of weights such that this function is very low for all of the inputs we want to make our neural network minimally bad。

😊，And so now this is just a simple optimization problem， right？😊。



![](img/1ce12f4ae7c2943f89de01fc24868ec4_26.png)

So what's a good？Function that we could use to tell us how good our neural network is well one possible such function is just the difference between what our output is and what the correct output is so if we take the case of this handwritten digit recognition task say that our network outputs a bunch of garbage here we would compare it to what the correct output is which is that every single class is zero and that the class corresponding to the actual digit is one。

And if we take the difference and square the difference。

 so we doesn't matter whether we're positive or negative。

 that that's a pretty good function to tell us how close we were to the true value。Right。



![](img/1ce12f4ae7c2943f89de01fc24868ec4_28.png)

Does this make sense to everyone？Okay， well now how do we minimize this function？We want to find。

 again， the set of weights that minimize the mean squared error function ideally over all possible inputs X。

 that would be all possible handwritten digits。So why shouldn't we also try to solve for the set of x's that minimize our function and just the set of Ws？

This is a multivari function， we have a bunch of w's， a bunch of x's。

superYeah exactly right this is just a sanity check because we can't we can't find that well we could find an optimal X and in fact sometimes people do that just to sort of get a view of how the network actually operates like by looking at what X makes the neural network maximally activate that we can potentially say something about what the network looks at you know maybe it likes the top of the handwritten digits more than the bottom but yeah no we don't have any control over the X so even if we did find an optimal X it wouldn't matter because we can't change it。

Cool， so let's find the set of weights， the parameters we can control that minimize our function。

And so the way that we do that is with this method called gradient descent。An easy way to do this。

 we take the partial derivative of this function with respect to the weights， okay。

 the only thing that we can control， and then we step in the direction of that derivative。

So the animation here we take the derivative and then we would step in the direction of this derivative and if we cross a minimal point we take another step and we just sort of keep iterating until we get to a point where。

You know， it would be a local minima， so the derivative is sort of close to zero。

 and that is how we know that our network is finished training。

Importantly we have to supply some step size parameter because when we look at the direction of the gradient or the derivative。

 we don't know how far to step in that direction， one thing is to ask all of you why can't we just include this parameter in our learning algorithm。

 why can't we learn this parameter like the rest of the weights？StizeYeah。

That's what you're trying to figure out first things。There's a more specific reason why we can't。

Because I mean it's not like we're trying to figure out the you knew what the step size is you would already know what the minimum of the curve is you would step right there I I guess I see what you I see what you mean that's。

That's a fair answer， but it doesn't mean we can't learn it， it just means that if we had it。

 we wouldn't have to learn it。That makes sense。Anyway， sure go for it。

Maybe you need the step sizeize to be adapted。Yeah。

 so that's we're going to talk about that very soon。

I think the answer that I like the most is how would you learn the step size？

With gradient descent but you need the step size to do gradient descent so like you know if there was a way to learn the step size。

 it would have to be with something that isn't gradient descent and gradient descent is is like the only way to do this optimization basically。

嗯。But yeah， all of these are good answers and we'll actually talk about the sort of adaptive step size like very soon。

And then eventually we'll converge once we do this process a lot of times to a sort of area where most of the gradients are around zero or at the very least we're bouncing back and forth across an area where the gradients are zero。

 but is this guaranteed to be the optimal solution you might be able to infer from the graph on the right but just because we found a minimum of the function doesn't mean it is like the optimal minimum and importantly this comes into play when we are initializing our neural network so depending on where you initialize the neural network where its starting point is it will fall into one of many potential mini and therefore like it's very hard to sort of get the exact same performance for a neural network over and over and over again oftentimes you could even like train the same exact neural network with the same data multiple times and get totally different ending acuracies。

Cool go ahead not at all I don't know if there are any good approaches for trying to find like a global minimum if that's even possible or like approximate Yeah。

 unfortunately it's just not even it's not even feasible to search because so typically you can say things about a global minima for convex functions and that would be all like sort of the classical optimization techniques deal with convex functions because it's something you can actually you know you can say that yes we will find the actual global minima the problem with neural networks is that they are so not convex it's not even funny。

 there could be like thousands and thousands of minima and they could go on for infinity like there could be mini like there's no way to exhaustively search all the minia of a function really。

Anything else， Na？

![](img/1ce12f4ae7c2943f89de01fc24868ec4_30.png)

Co right。So like I mentioned before， if you start your neural network at different points。

 like randomly initializing the weights in this case。

They might fall into one of many different minima and yeah this creates a lot of headaches when you're trying to sort of like replicate something from a paper because if you start their training with the exact same method and everything。

 but with a different initialization you just get different results。

 there's nothing you can do about it。

![](img/1ce12f4ae7c2943f89de01fc24868ec4_32.png)

Cool， okay， so taking this up into higher dimensions like that was 2D。

 we have to talk about this as gradients instead of just derivatives。

The direction of steepest increase or steepest descent， depending on your sign， is the gradient。

 and the gradient is the partial derivative of the function with respect to all of the different parameters and inputs。

In this case， we really only care about the gradient with respect to the weights and biases。

 so you'll see the partial with respect to the weights from layer one all the way down to the weight from or not layer one。

 but input one of the L length layer。And then， of course。

 the equation for gradient decent is a little bit self explanatory。

 but the weights of the n plus1 step is the weights of the end step minus the step size parameter times the gradient of the C function。

 typically called the cost function or loss function。



![](img/1ce12f4ae7c2943f89de01fc24868ec4_34.png)

Cool， all right。So another way to think of the gradient is just what happens when you nudge a particular weight so for a given input we can calculate the gradient and this is what it basically tells us what happens if you take a weight and you perturb it how large of an effect does that weight have on the output of this particular input and I like thinking of it this way because it basically shows you like say that I had a particular input you know say number three。

And there was a particular weight in the network that had a really large effect in the output。

I would like to take that weight and change it such that my output is minimized and the more effect that a weight has。

 the more I would want to change it。And so yeah， just to play the animation again， this is beautiful。

Yeah so actually the first time I gave this lecture I explicitly recommended to the entire class that they just go watch these videos before coming in because it'll just save me time and yeah I probably should have also sent that email to all of you guys but if you are curious after the lecture is done this first half of the lecture is basically following his video like step for them。



![](img/1ce12f4ae7c2943f89de01fc24868ec4_36.png)

不。All right， so a few questions to you all， so what are all the inputs to the cost function？Waits。

What else？呃，可能他是联系。Second。whatever actual is that we're carrying against。

Not to the cost function will。No， so you're actually correct。No okay， that's fair yeah。

 it's the the values of the actual true label have to be input to the cost function because otherwise you can't compare I didn't have that on the slides。

 but that's a good point。It's the weights and the actual correct label of the specific input。

Anything else？Yeah， the actual input of the function。And then the biases。

 which a lot of people say are just part of the weight matrix。Cool。

 so does the cost function change based on the input point？Yes， why。Got it， yeah， yeah， perfect。

 should it？Like if we were trying to actually get the correct answer for a gradient descent。

And we wanted to know how good our network is， should that depend on what was input to the network？

Really not。Yeah， ideally not。But kind of it's a bit of a trick question but I'm sort of asking this to sort of give you all a better intuition of this whole cost function stuff what we would really want is some sort of like distribution over possible inputs in the space so like I would like a set of all of the handwritten digits proportional to how likely they are for me to see in the real world。

Obviously we can't get that there's no way we're going to be able to create that sort of a data set and so the next best thing is we take samples from that distribution aK going out and collecting actual real world handwritten digits。

 and then we hope that on the data，That our error on this data set is representative of our error in the real world。

 that's not always the case because sometimes the procedure we use to sample handwritten digits are very different from the actual real world。

 so ideally the cost function should not depend on the inputs。

 but it always does and it's always very very annoying that it does。😡。

And then right so the rest of these questions are basically sort of in that vein when we calculate the gradient with respect to the weights。

 we're just calculating the gradient with only respect to weights and biases， not inputs。嗯。

How about this？When we're calculating a gradient step。

We have to do it with respect to a specific input， right。

 because we have to calculate costs with respect to one input。

Is that really the true gradient of the function or is that not quite what we want？

Im going to throw it over to you guys。I mean， the full gradient of the function would be like parameterized。

Everything that the function depends on， right。that what else do you do right right right well not just that but also like okay say that I wrote a very poorly written eight it almost just looks like a straight line like I was just very thin in eight right and I calculate the gradient and then I shift my entire neural network we update all 13000 weights so that I'm really really good at classifying that specific eight。

That's actually not what we want to do because we want to be good at all of the handwritten digits。

 not just any one particular digit， so in fact when you want to do gradient descent。

 technically the correct thing to do is to take every single input in your training data and then get the gradient update for all of them。

 average them all and then take one step in that direction and then do that over and over again。

However， technically， if you just step once for every single input， it approximates that。

 I'll talk about this later but。Taking a gradient step for a particular input isn't actually the same thing as gradient descent technically。

Cool， to get to step back a bit out of the weeds， so to speak。Let's talk about back propagation。

 we'll go into a completely new and annoying tangent。So。

I want to actually go through and calculate the partial derivative of the function with respect to every single parameter and go through what it's like to actually do this calculation the main reason why I'm going to step through this calculation is because in the next lecture we'll talk about how to optimize this calculation and so I want you guys to all be familiar with exactly this。

😊，Most people who do ML do not have to do this ever because all of the libraries basically just do this for you。

But if you guys are going to go and improve the libraries， then like you got to know how to do this。

 unfortunately。So。Let's start with the final layer we're going to do back propagation a computing the gradient for a simple。

I guess two layer neural network。On the final layer our equation looks like this。

 so Z typically denotes the outputs of the weighted sum and the sigma denotes the sigmoid activation function and then a is the activations like the things that are output by the sigmoid finally the cost function since we're at the last layer our activation is directly compared to the correct answer which is typically given as a y so our inputs are usually x outputs are usually Y。

And then the superscript just basically denotes what layer we're on。

 so the w of superscript L is the weights of layer L activations of layer L minus1 would be the activations of the previous layer that are being fed into this one。

Does that makes sense， okay， cool so the equations。

 we have weights times activations plus bias is the output of the linear layer。

 pass it through sigmoid and then we pass it to the cost function。

So we have to get the derivative with respect to the weights and biases and the way that we do that is we first start by getting the derivative with respect to the activations。

And of course， since this is a partial derivative， this is just chain rule， right。

 so the derivative of the outside is two times a minus y and the derivative of the inside is。What？

Yeah， right， so that's that。Then we go further back so we want to get the derivative of the activations with respect to the inputs of the activation and that's just the derivative of the sigmoid function right here it's denoted as sigma prime but the actual derivative is sigmoid times1 minus sigmoid you can do that out of yourself if you really want to。

And then finally， continuing back the derivative of the linear layer with respect to the weights。

Is just the activations because it's just a linear derivative， all simple calculus。Any questions？

Cool， so this gets more annoying the further layers you go back。So well， first off。

 it's important to note that when we want to get derivative of cost with respect to weights。

 we have to do the chain rule all the way back， so derivative of cost with respect to activations and then how the activations are affected by their inputs and how those are affected by the weights and then if you multiply them all。

 then we get the full derivative。So the further back you go。

 you just have to keep doing this over and over and over and over again until you get all of the weights even for the first layer。

And I've asked this question now for the third year， in the first two years。

 no one actually was able to get this， but technically speaking， this equation is actually wrong。

 but it's wrong in a very subtle way and I'm curious to see if anyone knows why this is wrong。

 even for the ML students this is usually hard。😊，Reminder that we're doing a linear layer。

When we're computing activations for layers before， there's something else we need to do extra。

We to unbied。What do you mean？哦。OhI was just thinking like this。Did we actually account for like the？

Bs term like when we yeah that's a good question I actually noticed as I was talking that we didn't talk much about the partial derivative with respect to the bias term and so thanks for mentioning。

Exactly， right， it's just constant and it gets multiplied by the previous term， so instead of a。

 it's just one。So。But thank you for pointing that out。A little more time。

Or what it's worth I also wouldn't have gotten this either， and I was kind of surprised。

 but so the annoying part is that because every single output of a layer is connected to all of the inputs of the previous layer。

We actually have to sum across the entire layer every time we go back one。

 so what I mean by that is so say I have a neural network and I have a set of activations right each activation of a previous layer is fed in as an input to every single。

Input of the next layer。 So instead of doing any one particular activation。

 you actually have to sum over every single output So you take the total sum of all of the the weights that were affected by a particular output neuron。

And then that is what's fed in backwards to the previous layer。

And so this is just a very small side note， but it does make the calculation a lot more annoying if we were able to do this element wise。

 this would be like extremely embarrassingly parallel but this。

ItDoes mean we have to accumulate every single layer as we're going forward。Everyone good。Alright。

 three。So now we've computed our gradient， now how do we actually use it？

So this is what I was talking about earlier when we actually do gradient descent the correct thing to do is to take one step for every past of the entirety of the training data so we take we calculate the gradient with respect to every single point average them all and then step once and then do that again for only one step this is very accurate it will take you directly towards the minimum but it's super slow obviously especially with like if I'm training on a million examples no way a good approximation is to take one step per each example this is often called stochastic gradient descent。

 not because there is anything inherently stochastic about it but it's just it really looks very stochastic like I like this graph a lot even though it's kind of very low resolution here this purple is the stochastic gradient descent this is often what it looks like when you get certain examples that are really really bad you'll just step in the total opposite direction of what the true minimum is but you hope that in expectation eventually will sort of converge to the minimum。

A good compromise is typically to just take a step per every like batch of examples。

 so you'll take like 32 examples and just average over them and that tends to smooth out a lot of the outliers or other like really bad examples in your data and not to sort of。

Beshadow what we're going to talk about on Wednesday too much。

 but this is really where GPUs shine because we can just do 32 inferences of a neural network in parallel We get all of the gradients in parallel because we do back proag at the same time and then we can just average it takes the same amount of time that's just doing it once so there's no slowdown。

Not no slowdown， but very minimal slowdown with taking batches versus stochastic readinging design。こ。

Oh， actually， before I move on to the next slide。This is something that always struck me as really funny having taken GP programming and then doing ML。

 a batch size of 32 is extremely popular， does anyone know why that would be？Yeah。

 it's a number of yeah threats in a warp exactly then no people do not know why this is but just like。

 oh yeah， right， we do 32 because of course we do 32 right。😊，O。Cool。

 so another quick like rapid fire round of really useful terms。

 just going to go over just basic ML jargon so that when I say it later。

 it's not confusing the activation function。😊，Is the nonlinearity we put in between the layers。

 the cost function or loss function tells us how bad we are and input representation is how we choose to represent our input as a vector for the handwritten digit problem that was very easy but for something like text。

 it's really not easy to decide how we represent our input as a vector and it has to be represented as a vector to be clear like this doesn't work if you don't do that。

The parameters are all the trainable numbers in a neural networks， the weights and biases。

 and the architecture is just how all of the weights and biases are connected to one another。

So the optimization method or optimizer is just the way that you actually compute gradient descent。

 everything is always gradient descent， but the specific optimizer is like。

You know how you actually decide the step size， whether that's adaptive or you selected you know a priori hyperparameters are parameters that are not learned and are just chosen like the size of your bench。

 the step size that you choose the the dimension of your neural network number of layers so on and so forth and then finally the initialization is the thing that you have as your starting point for the weights and biases a lot of people will say like oh why wouldn't you just start everything with zero。

It's a valid point， but a lot of sort of activation functions don't really like when things are zero and zero might multiply out and like zero out a lot of gradients so what people tend to do is they initialize by just randomly sampling a Gaussian between I don't know I'd say like negative one and one and then clamping。

哦。All right， final two things of jargon， the train test split or train dev test split is typically what you do when you're training a neural network。

 we take our data and we split it up into three sets。

 the training data usually roughly 80% is what you actually use to compute gradient descent the development data is what you use to decide what your hyperparameters are so you'll run the training using the training data and then you'll look to see if your choice of step size was a good idea or not。

 and then you'll change it and you'll see what happens on the dev data。

And then finally we have a third set which is the test data and that helps make sure that the accuracy that you got on your development data wasn't like unrepresentative。

 so development data you use to sort of fine tune everything in your model to get the best performance possible in the dev set。

 but that does mean that all of these parameters are very well tuned to specifically this set of data。

 so you want to have a third set to make sure that we're not like you know optimizing too much for one small subset。

对好。Maybe you're going to talk about this but how do you know how much data you need to oh you have no idea absolutely no clue typically you the intuition would be like try to judge how difficult of a problem you're asking the model to do。

Where difficulty is like very vaguely defined and then just collect as much data as you can。

 but you never truly know， and it's always the case that more data is always better。Always。

rusrating it is Everything about MLl is kind of frustrating。It's true。

 I mean you can't you can't know what the correct value for any of these things are until you run a huge training run like that's inherently frustrating。

Okay， cool， so just to recap train ontrain data， evaluate the performance on dev data tune hyperparameters and then report the results on the test data。

 typically you don't even run your model and the test data until the very very end and for a lot of very popular tasks you don't even have access to the test data you just or you would have access to the test data but you don't know what the labels are so you can run your models on the test data and then send the labels off to someone else and they calculate your performance to so that the labels are hidden。

The final thing is overfitting so if you fully train a neural network to conversion to convergence and you continue to update it over and over and over and over and over again on the same data。

You may run the risk of having the neural network be very。

 very well tuned to exactly this set of data。And then lose the ability to generalize to other data this often happens when you have a lot of learnable parameters in your neural network and the reason being that like if you have 13。

000 parameters，You may be able to just memorize every single instance of your training data like you can just say。

 okay， when the input looks like this， I'm going to output this value and just have basically a lookup table in a neural network and so if you fully train your neural network by looking at the examples over and over until you get perfect accuracy。

You usually just stop being able to generalize the way to solve this is just to stop training early。

 so you look at how good your accuracy is on your development data and if that goes down and then starts coming back up。

 it's time to stop training。哦。All right。All of ML on a single slide feel free to take a picture if you really want。

 but yeah so neural network is just a bunch of linear layers with a nonlinearar activation。

 the cost function tells us how bad our network is doing for a given set of inputs。

 weights and biases the weights and biases are learned from the data by minimizing the cost function through gradient descent gradient descent is just a process where we just initialize the weights and then update them by taking a fixed step size and then we calculate the gradient using back propagation applying the derivatives backwards from the point of the cost function all the way to the inputs。

Okay。Sure。I guess。Also maybe not answerable question， but it's for the number of liars in the middle。

 like is there any heuristic for like nope of course not。More layers is better， usually。

But you don't want to have like way more parameters than you have data so typically those two questions are answered at the same time where you say like if I have a ton of data great。

 I can learn more parameters like I can learn a 30 layer network。

 whereas if I have you know only 100 examples， I really should not have more than like1 thousand00 trainable parameters。

要得对。Cool all right so that's the end of the like hardcore like intro to ml stuff now we get to talk about the improvements that have been made to our basic setup that we've so far discussed so what we've talked about so far is just。

Linear layer， sigmoid， linear layer to do basic tasks。But。

This MIS data was released in 1998 and the three layer neural network that we just talked about got 97% in 1998。

 but people weren't talking about machine learning in 1998。

 they're talking about it now and yeah so what happened between then and now to take machine learning from something that was kind of useful and very niche scenarios and like useful broadly in like a ton of scenarios。

Also， I just want to mention that like these examples。

 the eight examples that I was talking about that's not a made up example。

 that's really in the data set， like if you see this like middle top one here。

 like that's a real number in the data set and you do get penalized for getting that wrong。😊。

So anyway， so like when a model gets 99。7， it's basically just perfect plus minus like some examples that I think humans would also disagree on。

Right。So the very first thing we're going to talk about as an improvement is actually the topic of what you asked recently。

 and that's the number of layers。So one of the reason why machine learning is so much better now is because we realize that adding more layers just directly improves the performance of models。

Almost across the board。Assuming you have enough data to train them of course。

 but when you hear people talking about deep learning。

 all they really mean is doing exactly what we just talked about。

 but like with like 30 or 60 or 100 layers and the deeper you go like intuitively the more complicated of a function you're able to learn technically for reasons that's not actually true because if you had infinite width and two layers you can technically learn any function。

 but with fixed width the deeper you go， you can in fact learn more and more complicated functions。

This has the side effect of being extremely expensive。

So the reason why you need a bunch of data centers is because as you make your networks just deeper and deeper and deeper。

 you just have to have more GPU compute to train them and the deep learning so-called revolution is only made possible by GPUs because it just you just can't run this much depth on a CPU。

It's like the complexity linear with the number of layers。没。Unmclear like。😊。

Like two times more layers means it's two times more expensive too。It's a good question， I。Yeah。

 I think so I think it would be linear with respect to the number of layers。But anyone that。

As has taken an ML and thought about this for longer is feel free to disagree with me there。

 I think that the complexity is linear。So the network we talked about had 13，000 parameters。

 but like， for example， g3 is said to have 175 billion parameters and then language models。

Well past the billions and this is when they stopped reporting how big they are because it was a trade secret so the latest number we have is 2021 so you can sort of。

Get off。You can sort of vibe what the curve looks like nowadays。

 I'm sure they're in the trillion no question about it。That's a lot of br。

Okay so why is adding depth really really good the theory of deep learning is still very young and in a lot of ways it's inherently resistant to having very like clean theorems on why things work because everything is statistics and everything is relative but generally speaking overparmeterization so having way。

 way， way more parameters than you need to in order to learn a function seems to lead to more high-level reasoning and better generalization because it sort of smooths out the lost landscape or it smooths out the gradient descent process if you have way more parameters you can learn functions more easily because you have a lot more high dimensions to work with this is hand wavy because it is and the theory is also equally hand wavy it's just a lot of empiricism and a lot of sort of pontificative。

Don't tell the theory about I said that。Okay。So the next thing is an improvements of the loss function。

Changing the loss function can drastically alter what is learned for obvious reasons because that is literally the thing that you're optimizing for instead of using the mean squared error function。

 which is just basically you know take the different square it so that it's positive no matter which direction is there a better loss function that we could possibly use for classification well one thing to consider is that。

Is that our output is a vector of size K， where K is a number of classes。

 and each class in the output vector gets a score based on the activation of the network。 However。

 our label。Is a probability distribution， all of the classes that aren't the correct class are zero and the class that is the correct class is one。

Just to sort of hammer home this。If our output of the neural network is zero for every single class。

 and then the correct class gets at 10。We actually would have a really substantial loss。

Because our output 10 minus1 is nine squared， that's a huge mean squared error。

 even though our network learned the correct output perfectly like 10 was the most or like the correct class was the highest value class。

 the problem is that we've decided that this activation is given a one。😡，And so in order to。

Make the output of the neural net into a probability distribution。😡。

We can use the softmax function and this takes a given set of inputs and converts it to something that sums to one and so in the previous example I talked about in the case where we had zeros for everything and then 10 as the most likely class this would be converted to zeros at everything and one as the most likely class and this inherently is way。

 way way better for training because it helps also smooth out like relative differences for example。

 if I had 0。7 versus 1。1 versus 1。3 once you take the softm it doesn't really matter as long as all of the other classes are much lower than the correct class we really don't care that they're zero right that's much less important than focusing on the fact that one class is better than the rest。

And this helps substantially。The motivation behind the explanation yes i'm really glad you asked that so I was actually just about to talk talk about that so you could have done this by just doing a linear sum on the bottom right you could just say that the top value is this number and the bottom value is the sum of all the other numbers right and that'll also sum to one the reason why we do the exponential is exactly what I was saying before which is so that。

When you have things that are very far away from the top value。

They contribute basically nothing to the loss right like we care about the top value and if you're using exponentials。

 the top value is going to be exponentially more represented in the final output than the rest of the lower values。

So that just makes it like much easier to learn because as you make the top value slightly larger。

 you get exponentially more and more like fewer and fewer like hits to the loss。嗯。

Does that make sense everybody is is。Good， good intuition。

So now if we have these two distributions and we want to compare them。

 we could do mean square error between them， but we need to we don't need to。

 but we should change our loss function to represent differences between distributions。

 one of the intuitions I like to say is the difference between like an 89% and 99%。

 the same as a difference between 59% and 69%。Mean squared error thinks that that's the case。

But if you've done。Probability that is absolutely not the case as you get closer and closer to 99%。

 you should get more and it's harder and harder to get to one like you're sort of exponentially more difficult to get to one。

And so there are plenty of functions for comparing probability distributions that are not just subtracting the different components。

And the main one that we use in classification tasks in machine learning is KL divergence。

 this is also typically called cross entropy loss， it's mainly called that because the functional form of KL divergence when you do a one hot vector looks exactly like cross entropy so they just say wow。

 it's cross entropy it's not it's kL divergence but the intuition is that these。

Talking about probabilities in log space scale better and better as we approach one。

 So it's weird because we we made these into probabilities by taking the exponential。

Then now we're in exponential space， so we actually have to go backwards with logs to compare probabilities in log space。

嗯。Another cool thing is that the derivatives are really， really clean for this loss function。

 mean squared error is nice because it's just two times the mean squared error。

 having natural log is always really， really easy。😊，So okay。

Recap so making neural networks deeper makes them better for reasons that are still somewhat unknown。

 although we are slowly figuring it out。嗯。When doing classification we want to output probability distributions because otherwise we get penalized for having really high activations。

 it's not good and then finally when comparing two probability distributions you want to use a divergence metric and not just like mean squared error and so we tend to use cross entropy loss。

Cool， okay。Moving on。We want to improve everything about the neural net。

 so I'm just going through all of the different improvements in the last basically 25 years of machine learning so next on the list is the activation function so we just kind of used。

The sigmoid function。 and then I just kind of brushed over and said。

 don't worry about why we're using the sigmoid What other options do we have for activation functions First thing has to be nonlinear It has to be smooth。

Because it has to be differentiable because we're taking derivatives through the activation function。

 if we have a non differentiable activation function。

 you can't do gradient descent or at the very least you can't gradient descent across the sort of discontinuity right。

嗯。So do we have to be between zero and one？I'll ask all you guys。I see one shaking head。喂食。

Do you want to try to answer？I mean， I don't even see why we like said theres zero somebody have to be putting zero low in the first place like hypothetically like I'd imagine that if you went just from like negative one to one。

 then like you would have biases near zero and that's just fine but。

I don't know I don't have great intuition behind this because I haven't the any machine learning no。

 but I think you're actually 100% correct and especially so for using softftmax on the output right Somax is already going to clamp everything from zero to one anyway so we don't really have to care if things are between zero and one during the network because we'll just softmax it at the end and we'll be fine if you don't softmax at the end then you might have to care。

But。😡，You really like you should always be soft maxing at the end for classification tasks anyway。

 so yeah， no you don't have to be between zero and1 at all， you do have to be smooth。

But you don't have to be zero one。Yeah， okay。Do you have to but like do you have to clamp between like some arbitrary range though okay so yeah。

 you can you could totally be like if you wanted to have like a well I hate like you can't have a line but like a parabola or something like yeah。

 you could totally do that。不是。That's a good question。Thinkaking of like it through。

'tI don't think it has to be monotonically increasing， no， no， no， it doesn't， it doesn't。

And the reason why it doesn't have to be monotonically increasing is that。If it's let's say。

 monotonically decreasing， you're just going to step in the opposite direction。

 it just flips the sign of everything。If you are changing the direction of your increase and decrease。

 likes say if you had x cubed or something as your activation。

It probably would make gradientding descent really hard。

Because as you're trying to get to a local minimum。

 it would add a lot of fluctuations in the lost landscape as you're going up and down the different things。

Most likely having something that's monotonic in at least one of the two directions is probably better。

 but that's a good question。So up here I have the hyperbolic tan function。

This also looks like a perfectly reasonable choice for activation。

 but it turns out that sigmoid is not great and hyperbolic tangent is even worse than sigmoid and the reason is。

Because when you get to really large values of the input， I kind of alluded to this earlier。

 but say that I had a weight that was like 100 and I wanted to change that weight。

Once you get to that point in the sigmoid function， your derivative is going to be what？

It was basically zero。What that ends up meaning is。In order to get a weight from 10ers。

 let's say an activation， not a weight right， let's say an activation going into the singularulator it's like 100 in order to learn that that's actually a really bad thing to do。

 you have to do a ton of gradient steps because the gradient is so small once we're at 100。😡。

It takes forever for it to finally get to this range in the middle where it has any like actual sort of momentum。

This was a really big problem when people randomly initialized their neural networks because every so often you would get a weight that was randomly initialized to some really high value。

 and then it would just stick here。In the sort of top sort of saturation range of the sigmoid function。

 and it would never come down， or at the very least。

 it would take like hundreds of gradient steps to come down。

This is what people call the vanishing gradient problem。

 we might accidentally saturate some of our activations and it would make the gradient go away even though we really would like that gradient to be you know very。

 very large and so I'll ask if hyperbolic tangent has this problem and I'll remind you that this is what the function looks like。

Yes， in fact， it's way worse because it clamps very quickly to negative  one and1 quicker than sigmoid。

So， and this was roughly， I would say like 10 years ago， maybe maybe more like 15。

But we found out that just doing something really， really simple， which is taking a linear function。

And then combining it with zero， so the max of zero and z。

Solves this problem and is' actually a really， really， really good activation function。Can anyone。

Gave a potential intuition as to why this is so much better of an activation function than sigmoid。

 it doesn't look like it would be a first。Well， so I guess the first question is。

 does it have the vanishing gradient problem？Definitely not in the positive regime。

 but why does it not have right？Do you want to try？

Just thinking from understanding this script that like for small weights。

 we don't really want them to contribute to the end result much anyways， so we want。

We like this behavior where it's linear in the high high values and then we don't really care as much what happens for zero I don't know Yeah no I think that that's correct I think especially like。

It's useful to allow the neural network to like turn certain weights off。

So if a certain weight we know is not contributing to the output at all。

 they'll just put a negative activation， that's the equivalent of saying like all right。

 we're killing it like this particular feature has no effect on the output at all done and then weights that are super positive will continue to stay positive and importantly the gradient will never be diminished once no matter how many res you go through because the derivative of relu in the positive regime is one。

So you'll never get a feature that's really important that does not have a gradient unless you are at your actual minimum。

嗯。I said that these functions have to be differentiable。

and then I immediately violated that by showing you a function that's not in fact differentiable everywhere this doesn't matter and the reason why is because we can just define the derivative at zero to be zero and now it's differentiable。

😊，Like I said， machine learning is very frustrating。😊。

What are the drawbacks of this sort of activation？I would say think back to when I was talking about the random initialization of the network。

好错。Trained to like to not converge quickly if your initialization start out in the negative definitely yeah exactly if you accidentally initialize your neural net and has a lot of negative activations you've just like turned off half of your network before you even started training and so yeah go ahead can you overcome that by just saying initializing everything as possible yeah that it's exactly what you do yeah pretty much but。

😊，You know with that， I think that like if you try to initialize everything as positive。

 you start to run into problems with sigmoid because again。

 or sorry with the softftmax at the end because if everything is positive， then really nothing is。

I think I think that that is what you would probably still do for ReLlu is just like you just make sure everything is positive。

 but there are other activation functions that aren't as bad as RELlu is in terms of this negative vanishing problem I'll just sort of go to the next slide and show you so a lot of the sort of papers that followed ReLlu。

Have done sort of different modifications to get rid of this sort of negative problem。

 probably because they didn't want to have to keep worrying about this initialization problem so the。

Glu， parametric Relu， leaky Relu is another popular one。From my understanding。

 Swig glue is the most popular activation nowadays， which is a combination of Galu and Swwish。😊。

Vaguely like this green curve， but it's more like the blue curve at the very beginning。

 I don't know again， very frustrating， but this the Swig glue paper been like 50000 times and all it is it's just like a fancier swish well but anyway right so there's a lot of。

😊，A lot of things you can do on purely just an activation function that'll improve your training significantly yeah go ahead so we even talking about like you know wanting to train T stepI yeah is this an instance where you see like a meta thing to train for the best activation。

That was terribly expensive。Maybe but every single time you wanted to evaluate any of these activation functions you'd have to you'd not only just train one neural network because that might get random biases you'd have to train a whole collection of networks average them on a particular task so yeah what you said it would be extremely expensive I think technically you could do it。

But then you would get into arguments about like， okay， so let's say for cost。

 we did a really small network because I don't want to have to train like billions of parameters billions of times and then people will say okay。

 but does this work on higher depth and then you say。I don't know。

But I think technically you could train it that way。Okay。Sweet。Okay， another really。

 really cool technique that people have figured out is this dropout technique。

 so for each weight in the network， we can just set it to zero with some low probability 0。

1 and this just basically helps the network to not over relyly on any one particular feature this is like extremely useful in the case where models memorize their examples。

Because if you've memorized a particular example， you'll have some subset of the weights that's extremely highly active and the rest of the weights that are kind of useless okay the weights that correspond to the memorization of the other examples。

😊，But if you use dropout。With 10% chance you just drop out the part of the model that memorize the example。

 suddenly the loss is huge and the gradient updates go to all of the other weights so this is sort of a form of regularization。

 which is to say。Some sort of thing that penalizes the neural network for not spreading out the function that it learns across all of the weights。

 typicallyyp we would assume that that would be better at generalizing because you're using more vector。

 the function is more complicated， so we want to encourage the neural net to use as much of its parameters as possible to learn the function。

Cool， another fun tidbit about this technique is that Google invented it and attempted to patent it back in 2015 and if it had succeeded in patenting this technique。

 anyone that used dropout would have to pay them royalties。

 which is absolutely insane and I'm glad that the patent was rejected and the machine learning community was not happy about that at all。

Okay， cool。Finally we'll talk about improving our optimization so what could possibly be better than vanilla gradient descent you may ask yourself well so let's maybe consider what happens when you pick a step size that's too big so。

If you have a step size that's too big， you may encounter this problem where you sort of bounce around the global minimum or the local minimum。

 I should say， but you never actually converge to it because your step size is too large and you keep getting larger and larger steps。

 and so you'll just pop right out of the minimum。On the opposite side。

 if your step size is too small， you may be。Converging correctly。

 but it may take you a really long time to get to this final point and all of the time spent training is just throwing away money basically because you could just have a better step size and get directly there。

So how do we potentially pick a better step size that will help us converge quickly。

 but not so quickly that we end up bouncing out of a localco minimum？So this is there。

The setup to what are called momentum based optimizers so momentum is typically just to add the previous step that we took to the current step plus some sort of decay parameter and so that is to say like if I have。

One step。I do gamma times the previous step and then add it to myself this generally helps gradientding descent pop out of small local minima so I like this diagram a lot where the ball is rolling down the hill and it gets to this sort of small local minima but there's a very large sort of chasm on the right side and because it has momentum from its previous steps it can sort of roll over that and then go over the hill。

So this is like extremely extremely useful this like improves the performance a ton one question I like to ask is when I do gamma times the previous step。

 does this only include one previous step？Or does it do more than that？

factoring and the momentum of the previous studies were right exactly so if you have the previous step。

That is also using momentum that incorporated something from the step before that and the step before that and the step before that so in fact for every update we have gamma times the step before and then gamma squared times the step before that and then gamma cubed times times the step before that all factored into the main loss term so in fact with this like very simple addition we've kind of have like sort of infinite squared tail of momentum so that's really really cool。

Um。But can we do better？So。This is something that and there a little bit。

In the weeds but I think it's important to mention because pretty much since 2015 this optimizer has not changed at all which is extremely rare in the machine learning world this is the adaptive higher order momentum so not only taking a step and scaling by the previous step but also scaling the step depending on the size of the previous gradient so not only the first moment but also the second moment and so this inherently gives more weight to rarer features just to talk a little bit more in detail this beta would be the decay parameter so this is the loss this is the previous step so VT minus1。

嗯。In the case of Adamom， we also want to divide by the square root of the squared gradient。

Which is to say not just the direction of the step。

 but the magnitude of the step as well square root of gradient squared would just give you like total magnitude of the feature and what this does is four features that are very rare like if I've only had one。

Let's just say one example that has activated this neuron。In the last thousand examples。

We should really take the opportunity to make a really large step because we're not going to see this neuron be activated again for a very long time。

😡，For neurons that are always activated， they're always going to get a gradient step， it's great。

 but for neurons that are very rarely activated once you have an example。

 we should really take advantage of that and that's kind of what the intuition is behind this atom optimizer。

 not only are you incorporating momentum， but you're also incorporating how relatively rare certain features are to get a step in the first place。

And this seems to be generally speaking the best we can do so far。

 I think every single language model that you've ever seen uses this optimizer。哦。All right。So recap。

Making neural networks deeper makes them better。Use softftmaxs to get a probability distribution and use cross entropy when comparing instead of using sigmoid。

 you should use Relu and probably siglu or Gelu or Swwish or whatever any other optimization function you want。

 this avoids the vanished gradient problem and gives you faster convergence use dropout for better generalization and then instead of using the normal mini batch stochastic gradient descent。

 you can use mini batch stochastic gradient descent with the atom optimizer which adds momentum and gives more weight to rare features。

So all of these are optimizations where we didn't have to change fundamentally the neural network that we were training。

 we're still training a three layer linear network， potentially more layers because of depth。

 but all of these other things are just better activations， better optimizers。

 and what better loss functions。😡，However， you can only get so far without actually changing the neural network itself。

So enough with these linear layers， let's talk about improvements to the actual architecture of the neural net。

So。If we combine more depth cross entropy loss relu dropout and atom。

 this will get you really good accuracy on the handwritten digit task so we get 99。

65 note that that's up from like 97， it's basically perfect， right？But。That task is not very hard。

What about for harder tasks with much， much larger inputs？

So one of the classic machine learning tasks is called INe or basically just object detection this is a data set of roughly six or I guess this is one million in train at 100。

000 in test of images that are all labeled for one of a thousand different object classes。

 so you have anything from like a dustitete to a containership mushroom。Maadaascar cat。

 that's just a lemur anyway。But yeah， so this task is way more difficult than handwritten digit。

 obviously， not only is it just like a larger selection of classes like our output dimension is 1000 instead of 10。

 but also like the actual dimensionality of the input is way higher。

So there's way more training images， 30 k versus 1。2 million the images are now of。196。

608 instead of our normal 784 dimensions。嗯。So one layer of a linear network。

 n times k right so 1000 times 196，000 is already 196 million parameters。

That's way too many tradable parameters for a single layer of a neural network。

 so we have to do something to reduce the number of trainable parameters because we can't just train something that's almost a billion parameters after one layer。

Okay， so how can we reduce the number of parameters we need one of the classic ways to do this is by just making assumptions about our input data that simplify the problem so。

😡，I guess I'll hand it to you guys， is there anything you notice about these images？

That we can take advantage of that helps make the image classification task easier。

Two images are like locations of each other or reflections of each other。

 or we say they're basically the same as。It was say reflective symmetry？

Anything else or reflective imvariance？Anyone else what about the pair of images on the right？

Oftentimes we can like identify some small subset of the image that is representative as what we actually want to class definitely so there's only certain regions of the image that may be of any use to us what happens if those regions are in different spots in the image does that change the object class at all。

No， right， we say that。Object detection as a task has translational invariance if we have an object in an image。

 it doesn't matter where in the image it is， it's always going to be the same object。

So using both of these things。😡，Can we help reduce the number of parameters？嗯。

Right so in the slide I say the same thing the objects in the image are translationally invariant and vanilla linear neural networks have to learn this because each pixel is its own weight right so if I were to train a linear network I would have to learn that a cat here is a cat but I also have to learn completely separately that a cat over here is also a cat because each of these regions have a totally different set of weights connected right this is obviously very bad。

The pro of vanilla neural network linear they don't assume anything about the input distribution。

 but if we want to make our networks better， we can assume things about the input distribution and then create neural networks such that we take advantage of those assumptions。

Okay so。In order to do this， we can introduce something called the convolutional layer and so what a convolutional layer is is you just take a filter。

 so this would be a filter it's a three by three grid。And then you can sort of。

Sweep it across the image。So you can imagine that a filter that would learn， let's say a cat。

 would be one where the shape of a cat has very high values like pi numbers。

 and then everything outside of the cat shape is very low numbers。So that when it encounters a cat。

 the filter lights up really， really large， and then when it doesn't it's back down to zero。And so。

Using these filters， we implicitly encode translational invariance because the filter is swept and is the same exact filter across every single spot in the image。

 and the filter says constant no matter what it is。So just to go over how this would look。

 you take our yellow filter。And we sort of sweep it across the green image and the output is the convolved feature。

 the output of the convolution right in this case， the yellow filter is this 101010101。Cool。

 this naturally reduces the dimensionality of the image。Um。Typically in ML classes。

 they have you go through and like compute given a certain filter of a certain size。

 what is the resulting output image， the computation is usually really annoying。Typically。

 in practice， we just add some border to the image so that it just stays in the same dimension。

And then if you hook all of this up and you use gradient descent on all of this。

 you'll get a network that learns optimal filters again。

 it's not really optimal because we don't have an optimal solution。

 but we have a network that will learn filters that correspond to things we would really want to see for object detection typically the filters in the early stages of the network will look kind of like this where it be very basic patterns like you know does something have stripes one way。

 stripes another way what colors does it have。But as you go down the network more and more layers。

 you get compositions of features， so if I have a filter that has certain stripes and then horizontal stripes I can combine them to get more and more complicated things like in this case when we get to the very low levels of the network towards the output you see clearly filters that look very much like certain objects so for example here's like a honeycomb pattern and the bottom left。

And then there's what vaguely looks like a goose， lots of car tires。

 a really famous study found that in a facial recognition network。

 there was like a specific Halllyberryrry filter like that was one specifically for her face and maybe that's just because she's overrepresented in the data set I don't know。

But yeah， so this is really， really useful and it cuts down on the amount of learnable parameters of the network by a ton。

Another thing we can do to take advantage of this translational invariance is by doing something called max pooling。

We just take a given dimensional region， so maybe the top left， top right， bottom， left。

 bottom right， and take the maximum value。In that area and just output the maximum value。

The intuition being。Answer the question does the object appear anywhere in this region and if so。

 you have the output right？How many learnable parameters are in this layer？None。

 it's just a function so we can do this basically for free and we'll reduce the dimension a lot note all of this is just trying to reduce the number of parameters we have to learn because when this was invented they could not load 196 million parameters onto a computer because it did not have enough memory。

So yeah， this is also very minor information loss because all we're looking for is whether or not the object is in the image at all。

 and so if it's in a region， then it's in the image。😡。

Cool so all of this put together is called a convolutional neural net。

 so a network that consists of a convolutional layer followed by a linear layer is called a CNN or convolutional neural net deep convolutional neural net so roughly nine or 10 layers do like really really well on vision tasks and the most famous example of this is this paper AlexNet from 2012 and a lot of people cite this as like the sort of beginning of what we would consider the current deep learning revolution。

This AlexNe paper is an eight layer deep convolutional neural network trained on GPU。

 uses Ra activations， drop out mini batch stochastic gradient descent with momentum。

 not atom wasn't invented yet， but it was implemented directly in KUDa for faster performance and it was trained with GTX 580s and this beat the state of the art accuracy by over 10% which is absolutely unheard of in the machine learning world。

Generally a lot of people will point to this is like the moment where people realize that okay。

 we should really be using GPUs and we should really do a lot of deep learning I keep teasing things for Wednesday but we'll talk a lot more about specific optimizations that AlexNet actually implemented and we'll even step through some of the code for the AlexNe network just to get you guys an understanding like。

The guy who wrote this was a GPU programmer at his core and decided， hey， wait。

 I should probably use my GPU knowledge to like revolutionize machine learning。过。

So a quick overview of what Alexnet looks like here has five convolutional layers and three linear layers importantly once we get to the end of the neural net and we have not a whole lot of parameters it's totally fine to do linear layers the problem is when you have linear layers with really really big input space so we use the convolutional layers to sort of reduce the dimensionality of our image。

😊，So we have an 11 by 11 filter and we have like what 55 of these different filters and then in the next layer we have a five by5 and we learn 27 of those filters three by three and we learn 13。

 so on and so forth， and then at the very end it's very common to just have a linear layer for all of those at the very end go ahead。

Convolal layers。Like。Is that to target like rotational invariance or do they just like target different filters like what is the Yeah。

 so it's mainly to learn more and more complex filters so if I were to go back to the the slide here。

Yeah。Cool so。Typically， if you only have one filter， you can't really get a whole lot of detail。

 but if you have a filter that can be an arbitrarily large composition of the filters from the previous layer like。

Take， for example， this filter。This like eyeball vaguely eyeball looking filter this can be a weighted sum of all of these filters in any amount of combination that it wants and the more layers you do。

 the more sort of power you give to filters and so it only takes a few layers before you can start learning like a goose basically so that's why。

Yeah。Cool as a side note I do think a lot of these filters are vaguely symmetrical。

 this isn't necessarily encoded， so the rotational invariance is not taken advantage of by a CNN。

It does seem like the network tries to learn filters that are， you know。

 like patterns rather than specific objects so that it can take advantage of rotational in variancevari。

 but all of the CNN is just taking advantage of translation。对。五。All right。

 so typically we do convolutions first and then we do the linear layers to finish it off。Um。

And right。Alex wrote custom coa kernels for all of these because no one had wrote GPU code to do neural nets and in the main paper goes into excruciating detail about all of the different optimizations right we use this block size this many registered this how much shared memory achieves 100% occupancy。

A lot of this stuff is like。Very typical for GPU classes。

 especially in the like you guys have done the optimization lecture where you just optimize the heck out of matrix multiply。

 right？That is what made the difference between machine learning， pre GPU and post GPU。All right。

I'm only going to talk about CNNs in this lecture next lecture I'll also talk a little bit about transformers and other networks like that。

 but this is just the tip of the iceberg there's a ton of different neural net architectures that all take advantage of different properties for example。

 like recurrent neural networks， take advantage of just arbitrarily long sequences of data that can encode some sort of memory over a sequence generative adversarial networks are really useful when you want to have a task that involves a loss function that's really hard for you to articulate。

 for example， an image generation task， you want to reward the network if the image looks。Looks real。

 like it looks like a real human fix， but how do you even like decide what that is？

It's not exactly a copy of a real human face， it wants to be like a plausible human face and GNs help you pit networks against each other where there's one generator that generates something and then there's a discriminator network that decides whether or not the thing that it produced is a real face and then they both have losses that sort of complement each other and all of these are exploiting some knowledge about the input data。

To recap。Deep neural network can learn anything。That is to say the vanillad linear layers。

 but they're not necessarily always the most efficient and they might take up way too many parameters if we abuse things that we know about the task。

 we can reduce the number of parameters we need。CNNs exploit this。

 this translational invariance to get away with training fewer parameters。

 and then we can use max pooling to further reduce the parameters and there's like a ton of different network architectures that take advantage of this。

Okay。So this is the last part of the lecture， thank you for hanging in there。

 I know this is really long but I'm trying to go over like。

A very large proportion of machine learning in one class。I need all of the three hours。あ。

But this is the fun part so I know a lot of you guys are thinking about machine learning with respect to final projects that you could potentially do for the class I highly encourage you to do a machine learning final project I think it's very clear that like a very large proportion of the people that are hiring GPU programmers are in machine learning and so having a project like this is always really really great。

😊，And there are a lot of projects that you could potentially do tons and I'll go over a few really like sort of easy starter ones。

And sort of try to give you an intuition as to what would be a problem that's really good for you to apply machine learning to。

So the first task we'm going to talk about is denoising， so the task is given a noisy image。

 output the denoise image。And the input can be either a black and white image RGB doesn't really matter as a side note。

 how do we deal with an RGB image I haven't talked about it but it was you know present in the imagenet。

 how do you deal with an RGB image when you use your like input representation。对。你。Okay。

You can grayscale it， that's a good point， I was not the answer I was expecting。

 but you absolutely can just grayscale the image and then just treat it as black and white image yeah。

Just zero one pixel you haveYeah exactly right so you can just instead of having each pixel be one value in the vector you just have it three does it matter where in the input vector you have the three values like does it matter if my red green and blue are all next to each other in the input vector or can it be there anywhere。

Well， I guess they should be adjacent for convol purposes perfect it depends on your architecture for a linear layer。

 it doesn't matter at all because all of the parameters are perfectly identical wherever they are for convolutions it absolutely does matter because adjacent pixels are are considered the same in the same filter typically what people do is they will have the red channel the green channel and the blue channel basically just be like a three dimensional image right they'll take like height width and then channels as like this and then they'll write their filters to be like 11 by 11 by3。

And so that's like their convolution filter anyway， sorry that's a bit too into the weeds。

 but I just figured that it was important okay so for denoing how do you think we can get training data for the denoing task this is always the thing you should ask yourself when when looking at an ML problem it's where do I get my data because if you don't have data you don't have a project。

So how do you get data for this task？Yeah definitely and I'm glad you said that because in previous years there's a lot of people that are like oh you know maybe we go and like compress the image or like we look for images that are really low quality that have also high quality versions the great part about the denoing task is that you can create arbitrarily low quality images for yourself if you have a high quality image right so if I have the original I just add Gausian noise to the image and then flip the task and then there you go I have my denoing task。

😊，One important thing to keep in mind though is that your noise actually looks like noise that you would encounter in the real world。

 so if I just add a noise pattern， I have to be sure that that noise pattern at least vaguely resembles real noise and not just some fake noise。

😡，One of the ways you can do that is by compression。

 so this is why AI upscaling is such a really easy task because。

If I have a 4K image and I shrink it down to like 1080p and then flip it around。

 suddenly I have a lot of upscaling data。Arbitrarily many and I know that NviIDdia does this for each individual game that it wants to use upscaling on so it literally will take frames from the specific game。

 render them in high high res and then crunch them down so it's even better data it's exactly what you would see in the real world that's why it works so well。

Okay。So once you flip it around， you can just learn a CNN so you take an image as the input。

 and then you want to predict the noise and then you can reconstruct the clean image by just subtracting off the noise from the original image。

嗯。Sure， let me ask， why do you think we should predict the noise instead of predicting the clean image？

对。The noise is the pattern that you're trying to learn like the image underlying image changes depending your yeah exactly exactly the underlying image is not actually the distribution we're trying to learn we're trying to learn separating the noise from the image right and learning the image is a lot harder than learning the noise because theoretically it's just straight up a simpler function right。

Yeah， so anyway I have a citation for a paper that did exactly this it just learned a CNN this is the sort of the figure from their paper note that BN is just batch normalization it's just basically making sure that no one activation is very large it's very easy to look up but otherwise it's exactly what we' just talked about and this paper has like what 10K citations or something because they just did the most straightforward possible thing and then it worked。

こう。So yeah， okay， sorry， 3600 citations since 2017。

 I think that that was input three years ago so who knows how many citations they have now？嗯。

Importantly question， why does it make sense for a CNN to be really good at this task？

Like of all the architecture you could use， CNN is still the state of the art， even now。

like I just laliness is sort of a like very image a local feature and that's the type of test of CNN Yeah exactly I like to think of it again like this is all intuition so there's no like real right answer but personally my intuition is like like especially let's say for this parrot image CNN is really good at using filters for specific patterns like I imagine if you had an eye filter with the bands around it you would learn that filter would go off regardless of if there is noise or if there isn't noise right and so sort of reconstructing what the original image under the noise is is really easy for CNNs because these small perturbations don't really affect the output of the filter as much。

So yeah。Cool， another one I mentioned this before， resolution upscaling。Given an image。

 scale it up to a higher resolution again。How do we get our training data？喂新丰。HsYep， exactly。

So you can learn a CNN for image upscal too， so you given a low rise image。

 predict the difference between the high rise image and the low rise image。

 use mean squared error loss because it's not a classification task。

 it's just a reconstruction task and then you do X plus R to get Y another paper roughly the same year did this on the citations。

😊，I almost don't need to ask， but why does it make sense for a CN to be really good at this task？

Same basic thing right you have the pattern that you notice even at low resolutions and that applies to high resolutions too it's the same pattern。

 so you can even look at this as basically a denoising problem because the noise is whatever the interpolations are between the different pixels。

😊，Yes， all right。So another one is frame interpolation。

 so given a video you can increase the frame rate of the video again。

 these are all like vaguely NviIdia sounding tasks right。

 but that's because how do we get the training data。

VideoYeah exactly it's beautiful right any time you have a task that you can just create your own training data you should immediately think like ML like the sirens should be going off in your brain and this is super common in moderate graphics because you can just render fewer frames you just render one frame every like you know three and you fill in the sort of frames in between。

😊，And so you can learn a CNN for frame interpolation， so you can do a 3D convolution across time。

 and so given surrounding frames and a filter that sort of crosses multiple frames in time。

 you can predict the interpolated frame， just use MSE loss。😊，Again， the citation。

So the results on this are pretty good， but they're not like unbelievable and so there's a lot of room to improve on this frame interpolation task。

 Lord knows what Nvidia is doing behind the scenes， probably using some transformer CNN combination。

 but just a direct convolutional neural net on this task isn't as good as the previous test that we've seen it's not quite state of the art。

So I'll ask this question， which is more interesting。

 why would it make sense for other methods to potentially do better than a convolutional neural net on this task？

Not I guess like the CNNs good at identifying the static patterns right there isn't really this temporal thing going onsI Yeah exactly I think at least my intuition is。

Say if I have a boat sort of moving across the screen right my CNN is just going to say a there's a boat in the image and then it'll max pool it to be boat vaguely in this area。

 If the boat is moving， I'm not going to know where in the interpolation the boat is。

 I'm just going to know that a boat is there so like when I generate I' I'll get the boat in the right spot。

But I won't have any sort of sense of like how much time has passed。

 where the boat should be sort of in sequence because I'm moving my filter across the image， right？

It's very hard for the network to sort of learn where in time this happens。Yeah， so anyway。

 that paper has a lot fewer citations than the other ones。

 probably because the method doesn't work nearly as well。

 but adding other components to the network to take advantage of and learn these time features might make a state of the art very。

 very small changes can produce huge differences in quality of output。Anyway。

 so right so the recap you can use deep CNNs for a ton of tasks。

 denoizing resolution superscal and tasks that benefit from an understanding of spatial locality almost always are done with deep CNNs even nowadays and CNNs has been around since like 19 like。

Definitely since the '90s， when MNIS was first created the handwritten digit recognition。

 that was the first CNN。嗯。The other thing is that tasks that can generate their own training data in some way are really。

 really good with machine learning and you can make the model as big as you want because you basically have infinite data。

Deep CNNs are not a silver bullet， but they're really useful for vision tasks and so feel free to try to trade a deep CNN for your final project。

 there's a lot of resources on how to do this。嗯。At the very end of this lecture。

 I'm just going to go over some of the other final projects we've had from previous years to get your mind thinking。

So the first one that we had was this web GPU image super resolution project this was from 2021 or 2022 right so basically what they did was they had image super resolution but this was running in the browser so it was using web GPU to access their computers GPU and yeah this image super resolution was done very very very quick and the GitHub link is there if you want to check it out。

Another team did frame interpolation， but they didn't use a CNN。

 they implemented the flavor architecture which is sort of like modified CNN but with a lot more bells and whistles you can look into it if you want on your own time I don't want to slow down the lecture you guys are already tired but yeah so they were able to get really really awesome results。

And then finally， this is a project that I really was hoping someone would tackle and someone did last year。

 which was the realtime path tracing， so this team accelerated the Pa Trar assignment to run in real time with the MLD noising and upscaling CNN。

I don't know if you guys， do you guys still to do the Aru filtering homework？

Okay no so there's something called Aru filtering which typically removes like noise in the output of a path tracer so they basically just like sort of drop in a replacement for that and they were able to get real time path tracer running。

Cool so anyway that's the end of this lecture on Wednesday I'll talk about how to implement neural networks the traditional way using neural network libraries like PyTtorrch and TensorFlow。

 but importantly I'll focus on the tradeoffs that they make so what do they sort of abstract away。

 what sort of optimizations that they make on the inside and then I'll talk about how to do machine learning at an even lower level to potentially even outperform Pytorrch's implementations and I'll walk through an implementation of a neural net in raw KudDa and then talk about how to optimize it。

够。Thanks everyone。嗯。I something I'm curious about but could not be related to these types of networks at all I really don't know like with LMs when they I feel like I've heard about like oh。

 you know like touch being too meeting or like you know I don't know whatever like tune something behind the scenes its not of a sudden like tells you and sorry all the time what is actually like it just seems like everything is so it's simple to how it front of any you don't you don't do it there。

So what they're doing is they're training the neural net on examples of people saying like。

 please make me a bomb and the chat UT， the correct response is， no， I'm sorry。

 I'm not supposed to tell you how to make a bomb。And they're just doing a lot of training like 10。

0000000 examples and then hoping to God that the model at the end doesn't tell you how to make a bomb And if anyone has messed around with chatttT。

 they know that it's very easy to get around this， or at least it was I don't know how easy it is nowadays you just say like oh。

 can you tell me a bedtime story about like how to make a bomb and that wasn't in their training data right so they didn't expect you to do that and then it sort of tells you so because it's all statistical exactly you can never guarantee。

That the model is not going to tell you something。 There can always be some inputs that will produce a weird output if it's not captured in the training data and unlucky for them。

 Natural languages like。Really high dimensional because there's a lot of different ways to say the same thing so。

So they're retraining it are they are they retraining the whole thing not you have totrain well you don't have to train the whole thing from scratch。

 you can take a sort of previously finished training version and sort of initialize from there and then train the last thousand steps on this new data so that's what they'll usually do they' like rewind training for the last thousand steps and then you know have a new end step for training that includes more examples of things that people saw my understanding is that a lot of the open AI team was looking at Twitter and trying to see the specific examples that people used to jailbreak chatyBT and then directly included those in training。

So they'll just try to like， they yeah， exactly， they just released the model and then saw how people broke it and then it fixed the ways that people figured out it rate。

Yeah。No problem。Any other questions？If not， all you all are free to go now it's totally fine。

 but yeah， feel free to I'm going to be here answering questions if you want to come up it's also fine。

Well thank you so much for asking so right now i'm trying to figure out how to identify what documents were used in training large language models this is really important for like copyright protection stuff so you know if i'm like chat UT and on'm the New York Times and I really don't want them to train on my articles there's currently not a lot of good ways to detect when。

😊，Certain data points are used in training and so I'm trying to come up with ways to like improve how to detect when something was used in training of a language model。

It is hard， I have some ideas， hopefully they work we'll see we'll see AI all the way down yeah。😊。

Yeah，Yeah， yeah， yeah I mean so。😊，I don't know， I worked on detecting AI generated text and like。

Yeah。有。A lot of people are asking the question of like。

How are humans different from AI and whether or not that's even like a really meaningful distinction because if you just say something well。

 like it doesn't really matter if it was AI generated or not so。I don't know。

 if you want to talk about that stuff， I could talk your ear off that's another hour and a half。有。

Yeah， I mean there's also been a lot of talk's a similar similar vein about， you know。

 like is this intelligence like a lot of people say no， but like we don't yeah， you have。

 we have no idea。When I first got into machine learning。

 if you talked about AGI you were laughed out of the room like we were it was literally like you were not supposed to say the word AGI because that just means you weren't serious about machine learning and like some point over like the summer of 2022 I started seeing actual smart people talk about AGI as if it's a real thing and I'm like。

What is this， I thought we were not allowed to say this word。

But no one knows what of this you were giving neural networks are based on the analogy of100% like what is the dog in a that seems like ethic I agree with you completely I think there's a lot of machine learning people that have the same intuition as you do it's just really hard to like we know that there is a lot more to be done especially with data efficiency right nowBT needs to read the entire internet in order to get the level of like a competent undergrad know undergrads don't read the entire internet so there's clearly some gap there and we kind of are cheating performance by just increasing the number of amount of data and increasing the depth and just throwing a ton of compute at it but if we were。

marter I'm sure we would be able to learn this way， way。

 way faster so yeah like there's a lot of work to be done on the modeling side and not just the data side。

 but usually you want to get state of the art performance and the way to do that in this day and age or data more compute so but that's good for GPU programmers because if you guys make compute fast like。

😡，That is directly bottom line of of these companies， you know。

 if you could improve neural network output by like。

Make it 3% more efficient that's 3% less money's they're burning so can you go back slide Yeah sure tell my Richard made in the presentation which one which one Oh yeah。

 yeah。HeI don't know， actually。😊，I wouldn't be surprised if they were but I'm just like okay so like the one where you like select which of these is like a sidewalk right don't they have to know that you have yeah they have to know before you even get shown the captures yeah like the first and then they use I wouldn't be really that surprised I think every company is trying to get data for free somehow whether that's scraping it from websites you're not supposed to scrape or taking advantage of like humans just on the internet generally to like annotate data for them so they don't have to pay for it I wouldn't be surprised and if not like some academics got to go find wherever that data is just give it yeah so anyway。

Oh， That's awesome。 Yeah， No， it is。 I mean， I I'm not electrical engineering background at all。

 but like。😊，I feel like a lot of the optimization classes and a lot of the core of ML came a lot from the electric already yeah that's a fair question to be honest with you because I at the beginning of me giving these lectures there were a lot of tasks that were like very obviously graphics oriented that weren't done yet and a lot of the lower hanging fruit。

 I feel like has been done that doesn't mean you can't do an ML project that does the same thing as them but just better for example right like these guys didn't just do image of resolution they did it in WebGPU on the browser like you can try to do something like that another really good ML project is just taking an existing neural network and then trying to make it faster just in general so like I know a group last year attempted to make so like architecture that is the underlying component of large language models called the transformformer。

The group wanted to optimize transformer attention to be faster than the like Pytorrch implementation they didn't quite get there。

 but it was still a really cool project it's just not as like visually flashy so I didn't put it on here there's a lot of projects like that which it's just like very raw like optimization Another one is like just taking a machine learning model and then like so so these guys this model was not trained by them right this is just directly off the shelf but just like implementing the inference of the model really。

 really quickly so implementing your own like harness to actually run the model yourself in raw kuda rather than using like Pytorch or something like that that's another good project idea but like I sympathize with with with the sort of。

The premise of like， well， they already did denoising and frame interpolation。

I'm sure that there are a lot of ML projects out there that are graphic oriented so something yeah 100% I think。

Funnily enough， convolutions are really， really common in audio processing。

 So there's something called the coner， which is convolutions and then transformer。

 So it's a couple of convolutional layers。 and then they just put it into a transformer。

 and I know that the。😊，I know that the original implementation of conformer had some like bug in it or something so there's a chance that it's also not the most optimal like inference so doing something with real-time speech processing and I also have some experience with that because that was my like Roblx internship I worked on like speech to speech translation so I could probably be fairly helpful I will warn it speech tends to be really annoying just because it's a lot of signal stuff but if you guys have the signal processing background then it would be a lot easier for you than it would be for other people but yeah like some sort of either speech synthesis or I mean speech dennoys even that alone would be very easy sort of follow on from this stuff it probably be good with CNNs too。

Okay we are also thinking of using jets and orange for the project rather than using。

Like the and we that we are been and to so on。Just so I'm remembering frankly。

 Jetson is like the sort of like the yeah， yeah， yeah， it's the sort of small like edge device yeah。

 yeah， yeah。I think that would be really useful for us to speech processing task like if you have some sort of I'm thinking of maybe like a microphone that's like a that's like an assistant or something that like wakes up on a wakeboard or something and if you if you just had a network that is' just constantly listening for a given set of wakeboards or something yeah like in Alexa like I've always kind of been interested in doing the like hardware side of that where is hard code yeah。

We have to hammer out the details by the way i'm like available over email if you want to if you want to email it and find about stuff。

I guess。I don't know if you want I can just tell you my email and you can write it down really okay know okay cool So this is this is good。

 I'm glad that my email comes off somewhere that's good。 and you can do also my office is town 297。

 So if you want to stop by in person but I think that like definitely speech is something that no one's done in any previous semester。

 It's always been vision related and fundamentally they're the same thing。 like you can sort of okay。

 they're not really the same thing。 but you know what I mean like you can treat them as the same in machine learning par and you can learn the same sort of networks。

 And then especially for an edge device it makes the most sense for that to be sort of speech。

 So I think that's a great framing， we just have to figure out what sort of network you would do whether you would train it whether you would just do the inference and then the last thing is that like。

An edge device really needs to be really efficient because you don't want to have to make it extremely large and so that's even better motivation for you to be like okay we've reduced the size of the network and we've implemented it super efficiently in like raw C++ so that it consumes less power so that this edge device can run for longer like very clean motivation for a project I think that would be great really unique too yeah yeah yeah so Ill do this。

嗯。W。I didn't know where the period he was Oh it's next to the spacebar do you think it's a better idea to train the network or should we look for available networks like because tomorrow I think we have to discuss the feasibility Yeah so so different groups have done different things so this group trained their neural net but they kind of had to because。

They were training it specifically to Denoys this path trace and so training really gave them a huge boost in performance the rest of these groups did not train their neural nets。

 they just took the weights from somewhere and then downloaded them I would recommend because your project is mainly on optimizing a neural net rather than training one to have good performance that you probably just download the weights from somewhere problem is that a lot of speech models。

Or at least when I was working on it， they didn't have their weights publicly available。

 they were all sort of hidden behind APIs， I think that's been changing。And that nowadays。

 models like Hubert models like。I don't know there's a lot of like song generation models that have their weights open source I would try to look for a model that is out there and has its weights available and then is that a good place to look for yeah so。



![](img/1ce12f4ae7c2943f89de01fc24868ec4_38.png)

Let me show you here I should probably stop the recording。Let's just。

