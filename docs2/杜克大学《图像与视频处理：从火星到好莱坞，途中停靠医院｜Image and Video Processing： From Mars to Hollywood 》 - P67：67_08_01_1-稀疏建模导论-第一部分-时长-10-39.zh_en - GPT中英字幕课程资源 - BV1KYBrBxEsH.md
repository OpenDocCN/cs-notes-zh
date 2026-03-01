# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P67：67_08_01_1-稀疏建模导论-第一部分-时长-10-39.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。 We're starting a new week in the area of image and video processing。

 The topic of this week is sparse modeling。 This is one of the most active areas in image processing currently and it's very important for us to describe this area we're going to be using some basic tools of linear algebra so there's going to be a bit of math but not as much as we had。

 for example， during the week on PDds and variational calculus and differential geometry and as before everything is going to be selfcontain and'm going to walk you through so it's going to be very very simple and you're going to be able to catch。

Everything that you need to know， the fundamentals inspiree modeling to understand， as I say。

 one of the most active current areas in the area of image and video processing before I proceed I should mention that I'm going to be using slides that I have adapted with permission from Profes alive and I want to let you know also that if you want to learn more about this topic。

 his book is an excellent source for that Of course you don't need the book everything is gonna to be self-con。

 you don't need to buy the book to enjoy what were gonna to be learning during this week。

 but if you want to pursue further this area， it's a good recommended source of material and there is also some other presentations on the web and also in the class webage in this class webpage we have listed a couple of places where you can get。



![](img/ab6726fd215e80a598360355d7a150c9_1.png)

Free software to play with this area。 So let's proceed to present what is sparse modeling。



![](img/ab6726fd215e80a598360355d7a150c9_3.png)

And we are going to use as example image denoicing sparse modeling is used for many。

 many other areas in image processing， but image denoicing is a good example to introduce the basic concepts So as we have seen before the basic idea is that we're going to have a noisy image。

Which we assume again just because we want a very simple presentation of the topic that we are having additive noise added to this image。

 so it's the image plus noise and we want to use sparse modeling to remove the noise so from a noisy image we want to do something to remove the noise。



![](img/ab6726fd215e80a598360355d7a150c9_5.png)

Now this can be formulated in the following form， which is type of a variational formulation that we have discussed before。

 but now we are in the discrete domain， so it's kind of a bit simpler。We have a couple of components。

Why is our image， the noisy image that's all what we have， we measure a noisy image。

And we want to recover a clean image that's X。 Now the first thing is we don't want the recover image to be too far away from the noise image and that's this penalization that we have here is the mean square error between the image that we observe and the image that we recover we have seen the mean square error for those that one understand a bit more what we are assuming here is additive Gaussian noise and basically we are minimizing and this is the variance of the noise basically now if we only had this term which fits the measurements then what's the solution to this problem。

 what's the image that minimizes this problem is nothing else than the noise image itself So we haven't done much。

And that's when we add another term that has multiple names depending on the discipline is called a prior。

 it's also called a regularization term that basically says yes， I know an image。

 I know I want an image that is close to Y but I want that image to have certain properties let me just illustrate one example。

 let's assume that this is your data， I'm going to just mark a few points。This is your data。

 this is y if I tell you nothing else but find x that is close to y， you're going to stay with that。

But if I tell you that through this function， if I tell you that the solution is a straight line。

 I force you to make a straight line， then you're going to find a solution which is something like that。

not the original points， but something like that， so I gave you prior information。

 I gave you a constraint that says find something that is closed。

 but it's also a straight line and then you got that solution。

So the basic idea is that we have two terms， one that relates the solution to the measurements。

And one that basically gives you a prior a regularization a condition so it kind of we are projecting the observation Y into this prior Now this is what's called a Bayesian point of view following Thomas base and the basic idea is that we're computing what's called the maximum aosteiri or the map we're basically going to compute。

The X that maximizes something or minimizes this function。

 depending if we take the function as itself， we call it a minimizer。

 if we look at the probabilistic framework that is basically an exponiciation。

 So we take this to the exponent and this also kind of to the exponent， there will be a maximization。

 but don't worry， we do max or we do mean depending on the sign。 and depending we can always do。

Minus， and then we get a maximization。 So that's what is's called the maximum a posteriary。

 We could give to everything that we' are going to be presenting next， a probabilistic framework。

 a probabilistic interpretation and then make this even more clear。

 But the basic idea is that we have a prior and in base language， this is called a likelihood。

 the prior and the likelihood。 and both can have a probabilistic interpretation。 Now， once again。

 this models the noise， in this case， additive Gaussian， this models the signal。 and a lot of image。

 and in general signal processing has dedicated a lot of effort into designing what is the best prior。

 what is the best space to define images to define different types of signals。

 and it has been a lot of work in the literature of。Image processing in that。

I'm going to just describe a few people say a good priority is give me an image that doesn't have too much energy。

 so this is this example， there is always a parameter here that can scale it up and down。

There were other priors that say give me an image that is smooth for example。

 we have seen when we talk about in painting that one way to measure smoothness is the lapplian。

 instead having low energy you say it has to be very smooth。

 which means that when I compute the lapplian， the energy has to be low。

Another prior is to say that's correct， but we have edges， so I don't want my edges to be smooth。

 I want very sharp edges and then we do an adaptation that says not every place it has to be smooth。

 we allow certain jumps。Another example is to basically take functions。

 not just the quadratic functions， but more sophisticated functions of smoothness and that's related to the topic of robot statistics just another example we can talk about total variation we have seen that when we did anisotropic diffusion this was one of the examples of anisotropic diffusion that we took basically the integral over the gradient。

 not gradient squared by the gradient and we got anisotropic diffusion。

We can also do wavelelets and we haven't discussed in this class about wavelelets。

 but you probably have heard about wavelelets as a very important topic in image processing。

 of course in nine weeks we cannot discuss everything so we have not discussed about waveleletths in particular。

 but people have used that and you can think about basically multiplying the image by a matrix and then doing some penalty on that product。

 for example the L1 as we have here the absolute value。



![](img/ab6726fd215e80a598360355d7a150c9_7.png)

What we are going to be discussing during this week is this particular prior。That we have here。

 And I'm going to explain it more in the next few slides。

 and were going to even learn more in the next videos。

 But this is the prior that we're going to be talking about。 And basically， it's written here。

 But again， I'm going to explain it next。 This has been basically the evolution and。

Basically is kind of historical evolution though't know exactly about different types of priors that people have used that people have proposed。

 Each one has its own advantages and disadvantages and we're going to discuss this one Now there is much more sophisticated priors that people have proposed in the literature some of those are very good but are computationally extremely expensive and extremely difficult。

 One of the virtues of many of these priors and as we're going to see also of this one is computationals are feasible we can do them。

 we can understand the prior and we can do the computations So let us explain what is this prior of sparse modeling。



![](img/ab6726fd215e80a598360355d7a150c9_9.png)