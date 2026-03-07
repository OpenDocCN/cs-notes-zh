# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p13 P13 -BV1zNSCBkEgW_p13-

![](img/ef79c89b2968b9a9b03ddba93d98ebf4_0.png)

Yeah， so well thanks for coming so my name is Rongge。

 I'm a postdoc at Microsoft Research just down the street。

 so Gelani is not here today and I will be giving a guest lecture。So。Its pretty for more。

WellSo today I'm going to talk about learning topic models。

 which is part of a research that I've been doing， we are trying to apply the algorithm design techniques in theoretical computer science。

 the stuff that you have been learning through this course to machine learning problems and to get algorithms for machine learning problems。

So please stop me anytime if you have any questions。

Gellani told me that someone is going toscribe the Oh， thanks。

 So if you need anything you can send me an email。Yeah， so。

So let me start with some very brief introduction to what are the machine learning problems that we are interested in。

Of course machine learning is a very broad area， machine learning takes several courses to explain。

 so I'm going to explain only the parts that's most relevant to the topic models that we are going to talk about today。

So in general， there are many kind of learning problems。

So it's the most popular machine learning problem that。

People most often try to solve it's called the supervised learning problem。呃。

So in supervised learning， it's like you want to learn a spam filter。

 you are given an email where you are actually given a lot of emails and you have labels whether these emails are spam or not。

And the goal is to learn a function that。The goal is to learn a function that given a new email。

 you want to know whether it's spam or not， and that's called supervised learning。

In supervised learning， we are given both data points and labels。

 and the goal is to given new data points we want to predict its label。

But that's not the kind of learning that we are going to talk about today。

 so by the way supervised learning is very well studied under the name computational learning theory for many decades and there has been a lot of beautiful theory but again we will not have time to touch any of those today。

It's a problem that we are interested in is different because。

They are called unsupervised learning problems。An unsupervised learning problem。

 the idea is sometimes it's very hard or costly to get the labels。Usual to get the labels。

 we will need human to label all the documents or emails or whatever you want to classify。

So the idea of unsurprivised learning is what can we do without labels？

So in unsupprivised learning the input to the problem。We will just be data points。

X in whatever space that I will not specify。Think of， for example， you have。

A bunch of points given usure data for the unsurprised learning problem。

And but given these data points without any labels， what can we hope to do， Well。

 one thing we can hope to do is to。To learn the structure。嗯。Of data。

So one thing we can do with just data points without any labels is we can say maybe this data has some pattern or structure that's hiding in the data and we want to find that。

For example， in this example， one possible structure is maybe they are。These three clusters， and。

Maybe these clusters have some meanings。So clustering is a classical example for。

For unsupervised learning in clustering， you are just given these points and the goal is really to find a certain number of clusters so that the points。

Within the same cluster are similar。And points between clusters are farther away。So。

So that is the kind of problems we are interested in unsupervised learning。嗯。

So one of the important problem in unsupervised learning is。So as I said。

 our goal is to learn the structure in the data。So how can I specify what is the kind of structure that I want to learn。

 for example， in this example， I want to learn a clustering。

 but what other kinds of structure might be available in the data？

So that's not always very easy to define and。In machine learning。

 there's actually a very popular way to define this structure。So， defining。Structure。

So the popularity way of defining structure is to use a probabilistic model。

So what is a probabilistic model well a probabilistic model。

 well first it takes in some parameters for the model。

And then the model will tell you how to generate a set of points。And the parameters will will be。

The kind of structure we are looking for。 So this might be a bit abstract。

 let me first give you the definition。A probabilistic model。By the way。

 this is an informal definition。Its a function。呃。So maps。parametermeter CP。To data distribution。

AD of theta。So， then。For example， one of the simplest probabilistic model is maybe just a Gaussian random variable。

For a Gaussian random variable， we can specify the mean and variance of the Gaussian variable。

And once we know the mean and the variance of the Gaussian variable， of course。

 we can sample points from this Gaussian distribution。And that's quite easy。

Then the learning problem will correspond to given many samples from the Sculsian distribution。

 I want to estimate the mean and the variance of the Scul。

So the learning problem is really the inverse of the data generating process。

So the Gaussian problem might be a bit too simple。 So let's look at。AMore complicated example。

That's called a mixture of Gauss。A mixture of Gaussian's model looks well。

 The data points will look kind of like this。 So basically。

 the assumption is or the model says the data points should come from one of say， K Gausians here。

 K will be equal to 3。With some probability， say with 0。4 probability。

The data point will be generated according to this Gaussian。And maybe with 0。3 probability。

 the data point will be generated from thisus and with the rest 0。3 probability。

The data points are going to be generated from discussion。嗯。So in order。

 if I know all the parameters of the model in order to generate a data point。So what I do。

