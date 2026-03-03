# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P13：-13-Advanced Algorithms (COMPSCI 224), Lecture 13.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/e2b2444301a608b2cfc8549846926cbb_0.png)

Yeah， so well thanks for coming。 so my name is Rongge。

 I'm a postdoc at Microsoft Research just down the street。

 So Gelani is not here today and I will be giving a guest lecture。So。Sp one not。

Well so today I'm going to talk about learning topic models。

 which is part of a research that I've been doing。 We are trying to apply the algorithm design techniques in theoretical computer science。

 the stuff that you have been learning through this course to machine learning problems and to get algorithms for machine learning problems。

So please stop me any time if you have any questions and。

Glani told me that someone is going toscribe the Oh， thanks。 So if you need anything。

 you can send me an email。Yeah， so。So let me start with some very brief introduction to what are the machine learning problems that we are interested in。

Of course machine learning is a very broad area， machine learning takes several courses to explain。

 so I'm going to explain only the parts that's most relevant to the topic models that we are going to talk about today。

So in general， there are many kind of learning problems。

So it's the most popular machine learning problem that。People most often try to solve。

 It's called the supervised learning problem。呃。So in supervised learning。

 it's like you want to learn a spam filter， you are given an email where you are actually given a lot of emails and you have labels whether these emails are spam or not。

And the goal is to learn a function that。The goal is to learn a function that given a new email。

 you want to know whether it's spam or not， and that's called supervised learning。

In supervised learning， we are given both data points and labels。

 And the goal is to given new data points。 We want to predict its label。

But that's not the kind of learning that we are going to talk about today。 So by the way。

 supervised learning is very well studied under the name computational learning theory for many decades and there has been a lot of beautiful theory。

 but again， we will not have time to touch any of those today。

It's a problem that we are interested in is different because。

They are called unsupervised learning problems。An unsupervised learning problem。

 the idea is sometimes it's very hard or costly to get the labels。Usual to get the labels。

 you will need human to label all the documents or emails or whatever you want to classify。

So the idea of unsurprised learning is what can we do without labels？

So in unsupprivised learning the input to the problem。Will will just be data points。

X in whatever space that I will not specify。Think of， for example， you have。

A bunch of points given as your data for the unsurprised learning problem。And。

 but given these data points without any labels， what can we hope to do， Well。

 one thing we can hope to do is to。To learn the structure。嗯。Of data。

So one thing we can do with just data points without any labels is we can say maybe this data has some pattern or structure that's hiding in the data。

 and we want to find that。For example， in this example， one possible structure is maybe they are。

These three clusters， and。Maybe these clusters have some meanings。

So clustering is a classical example for。For unsupervised learning in clustering。

 you are just given these points and the goal is really to find a certain number of clusters so that the points。

Within the same cluster are similar and points between clusters are farther away。So。

So this is the kind of problems we are interested in unsupervised learning。嗯。

So one of the important problem in unsupervised learning is。So as I said。

 our goal is to learn the structure in the data。So how can I specify what is the kind of structure that I want to learn。

 for example， in this example I want to learn a clustering。

 but what other kinds of structure might be available in the data？

So that's not always very easy to define and。In machinesine learning。

 there's actually a very popular way to define this structure。So， defining。Structure。So the。

 the popularity of defining structure is to use a probabilistic model。

So what is a probabilistic model well a probabilistic model。

 well first it takes in some parameters for the model。

And then the model will tell you how to generate a set of points。And the parameters will will be。

The kind of structure we are looking for。 So this might be a bit abstract。

 me first give the definition。A probabilistic model。By the way， this is an informal definition。

It's a function。呃。So， maps。parameterarameterceta。To data distribution。AD of theaterta。So， then。

For example， one of the simplest probabilistic model is maybe just a Gaussian random variable。

For a Gaussian random variable， we can specify the mean and variance of this Gaussian variable。

And once we know the mean and the variance of the Gaussian variable， of course。

 we can sample points from this Gaussian distribution。And that's quite easy。

Then the learning problem will correspond to given many samples from the Scul distribution。

 I want to estimate the mean and the variance of the Sc。

So the learning problem is really the inverse of the data generating process。

So the Gaussian problem might be a bit too simple。 So let's look at。AMore complicated example。

That's called a mixture of Gauss。A mixture of Gausian's model looks well。

 The data points will look kind of like this。So basically。

 the assumption is or the models says data points should come from one of say k Gausians here。

 K will be equal to 3。With some probability， say with 0。4 probability。

The data point will be generated according to this Gaussian。And maybe with 0。3 probability。

 the data point will be generated from thisus and with the rest 0。3 probability。

The data points are going to be generated from discussion。嗯。So in order。

 if I know all the parameters of the model in order to generate a data point。So what I do。

 I first choose which Gaussian the data point should come from。Maybe it's this one。

 and then I will sample a point according to discussion and maybe it will be here。

But what's important of course， is once I have this data point and I gives this as the input to some unsupervised learning algorithm。

The algorithm does not know that this point is really generated from this particular Gaussian。

 It only sees all these points， and it really has to kind of figure out。Which Gausian it came from？

And that's。The hardness of this kind of problems。Any questions？Okay。

 so let's first summarize what are the parameters of the mixture of Gausians model？

So there's the number K， which is the number of Gaussians。For each Gaussian。

 we want to know what is where it's its center， where it's the mean of the Gausian。

So we have the vectors mu I。I puts a vector symbol here， so I is from 1 to k。So when I write this。

 I am in the set of 1，2，2 K。So these are the means of the Gaussians。And for simplicity。

 let's assume all the Gaussians are spherical， although I didn't draw it this way。

 so all the Gaussians are spherical and they have the same covarience matrix and we know that so that's not a part of parameter。

😊，So what else is there in the parameters？Well， in order to generate these data points。

 something that we also need are also these spaces。

 like what fraction of data points come from these individual Gaussians。

So they are also part of the parameters。 So let's call WI。I is also in 12K。These are the weights。

Of the Gausians。So now given all these parameters， it's clear how I can define a distribution on the points。

 and if I really know all these parameters it's actually simple for me to sample a data point from this distribution。

 right？But then the corresponding learning problem。Learning a probabilistic model。

So the problem is then given samples。Given maybe polynomally， many samples。

Polynom million number of samples。Say V1 V2。 Well， Let's just not give the names。

 Give these many samples from。distribution D of Cta。For。An unknown sitta。Given all these samples。

 our goal is to really find this unknown parameter theta。Yes。何にし？Right， so。Actually， I mean。

 you are in the problem you are given an oracle access to an oracle that when you query。

 you get a sample from the D Cta。呃。If your algorithm runs in polynomial over the time。

Your algorithm is allowed to depend on anything。 It doesn't even necessarily need to take polynomial number of samples。

呃。It's just the kind of theorem you write。 It can be a very strong result。

 or it can be a trivial result。 For example， maybe we can learn a mixture of Gaussian in n to the K time where n is the number。

 Well， in say， D to the K time where D is the dimension。Even that is not so simple。

Or we can hope to learn it in。Poly and D and K time。 That's even harder。

 So it all depends on what you want。 So this is， that's why it's in bracket， so。Re。

 you should think you have an oracle access to this distribution。

So given some number of samples that you can。Qury from the Oracle。The goal is to learn。嗯。Find。

Ideally， we want to find the exact parameter Cta。But usually we cannot do that。

 and we will find an approximate version of Cta。Here it's really important that we are allowed to output an approximate version。

 because in general。Even if we don't care about computation time。

It's usually impossible to get the exact theta， even if it's a simple Gaussian。

 I give you many samples and you want to estimate as min。

You just take the average of all your samples， but that still hasle distance depending on how many samples you use。

So usually we can only hope to find an approximatezeta also with high probability。

 because there's always a chance that the samples youll get are not very informative。

So this is really the learning problem， the general unsupervised learning problem that we want to solve。

呃。And it's not very easy to solve this kind of a problem in practice， there is actually a。

An approach that's used in solving many of these problems。

And that approach is called maximum likelihood。It's one likelihood。

So the idea of maximum likelihood is I have all these data points。And I。

I know what is the model if I have a fixed parameter。

So my goal will be I will find a model within this family or I will find a particular parameter。

Such that this model will have the best probability of generating the data that I've seen。呃。So。

 the idea is。We'll find。The model。That that。Maximize。The probability that。So。

Data comes from the model。Usually we assume we get independent samples from this distribution D Cta so。

呃。So， suppose。Data points。Our。Say we  want2， V end。

Then what we want is we want to compute this maximize over all the parameters。Some I from 1，2 K。

to end。Log of probability of。Bi。So we want to solve this optimization problem。

Here I wrote a sum of log of probability。 This is really maximizing。

 this is really the same as maximizing the product of these probabilities， which is what we want。

And well， people often write it this way because it's easier to。 Well。

 it's conceptually easier to think of maximizing a sum instead of maximizing a product。嗯。Okay， so。

So this is the so called maximum likelihood approach。

 It can be applied effectively for some very simple distributions。 For example。

 you can try to do maximum likelihood for a single Gaussian。Then。Basically， this。

 this will be something that's very easy to solve。 And you will see that the min will really be the min of the samples。

 so which is reasonable。But this problem is really very hard to solve once you go to some more complicated models。

 for example， if you try to do maximum likelihood。For this mixture of Gausians model。

 it will be NP hard。 It is at least as hard as doing cameian clustering。Which is itself MP hard。嗯。

So actually， it's worth mentioning that if you think of these， we， these data points are。

Come from are just arbitrary data points， they may not come from the distribution then it actually trying to solve a more challenging problem。

嗯。If Vs are。Not from。This distribution D seeta。And when I say MP hard， it's of course。

 referring to this case because this is a worst case problem。

And learning a probabilistic model problem， this particular problem where the data points really come from D of Cta。

This is not really a worst case problem， so we cannot say it's NP hard or anything。P way， I， sorry。

 I didn't define the problem。 The P Cta of V I， but P Cta is just the density function of the distribution D of Cta。

呃。So now we want to solve this learning probabilistic model problem。

 but the most popular approach turns out to be MP hard。So how do we deal with the MP harnessness。

Any idea how to how do we usually deal with MP hard problems。Right， so so in this lecture。

 you've learned approximation algorithms。 And that's a very nice way of。

Dealing with MP hard problems。And in many cases， approximation does make sense， for example。

 if we want to do a k means clustering and if the data points are really like this。

Then maybe even if I get a， say， a two or three approximation。

 the clustering could still be quite reasonable。呃。But if the problem。

 if this maximum likelihood problem does not have a very special structure。

Sometimes it's not clear what can approximation algorithm do。Because we are maximizing。Really。

 this is an active number because it's a log of probabilities。So we are maximizing that。

 or we should really be thinking we are minimizing the negative version of that。Usual we can。

 for most problems， we can only get a constant factor approximation。

But a constant factor in the log probability space does not correspond to a constant factor in the probabilities。

 right， Because if the logs are within constant factor。

 it doesn't mean that the E to the Z number is still within a constant factor。In fact。

 the Cta we get might give a much lower probability than the optimal theta。So， in many cases。

It's not clear what approximation the algorithm can do。And， of course， another thing here is。

As I said， we are。 well， the best case is， of course， if we can solve this worst case problem。

 we would be happy， but that only happens for very special problems。

We will also be reasonably happy if we can solve this average case problem。

 where the data actually come from the of Cta。😊，And that's potentially much easier than the worst case problem。

Or more realistically， we might。Really want to solve something in between when the data points are roughly generated according to the of theta。

 but。Let's not go into that。So average case is also。

Possiities that the MP harnessness might go away because of that。

Average case also includes sometimes we have some idea of what these means of the Gaussians say might correspond in some real system。

And the real system might have some way of generating these min。 For example。

 maybe we can assume these min of the Gaussians are also random vectors of some sort。

That may further simplify the problem。And the third idea。

 and actually that's the idea we are going to most focus on today for topic models。

Is to come up with natural assumptions。Again， this is a mixtureer of Gaussian's problem is quite abstract and can be applied in many settings。

Maybe in some systems， these means and weights have real meanings， and we。From that。

 we can have natural assumptions about those particular parameters。

And those additional restrictions might allow us to。Have a faster algorithm。啊。

And you will see an example today。 And finally， if none of these works， we can always。

Try to use a heuristic algorithm。And hopefully it works okay in practice。

So none of these points are actually mutually exclusive。呃。You think。

Using a heuristic algorithm doesn't prevent shouldn't prevent us from trying to analyze the heuristic algorithm using either average case analysis or under some natural assumptions。

So it was a real hope for。What。For this kind of research is we have a heuristic algorithm。

That applies in practice， that works in practice。But we can also analyze in under。Can analyze under。

Well， either approximation sense or average case or natural assumptions。Under approximation。

Average case。Or assumptions。Or whatever else you can think about， you can think of。A。

So this is3 our hope。We know this is possible for a small set of problems。 but in general。

 this is really。New area and a relatively new area， and there are still many open problems in here。嗯。

So today we will see an algorithm that's different from the heuristic algorithms that people have been applying before。

And that can be analyzed under natural assumptions for learning topic models。嗯。Okay。

 so now let's get you。Really， what is the problem。 I wrote the title half an hour ago。

 but I haven't been explaining what， what do I mean by learning topic models。呃。So。

 so what are topic models。So topic models is a way to try， so。

So it's easier to first define what do we want to achieve by。Learning topic models。

The goal is to learn a semantic structure。From。A large corpus of document， a large tax corpus。啊。So。

 for example， if I take New York Times articles for， say。

20 years and I try to learn what are these articles talking about。

 some of them might be talking about， say， politics or sports or science。

And which documents are talking about these different topics for each different topic。

 what words are used when we are talking about these topics？

So we want an algorithm that can automatically learn how those information from just a bunch of text documents。

And tests really the goal of topic models。It has many applications， but。Let's not go through that。

So this is a goal。 And the way we do it is， as I suggested， this is a unsupervised learning task。

 and the way we specify what we want to do in unsupervised learning is often through a probabilistic model。

So these probabilistic models are called topic models。

So a model should specify under some parameter how to generate data distribution。In this case。

 the model should specify how to。generaterate。Documents。But of course， if you think about it。

 it's not so easy to generate a document。 We， we all write articles， but at least for me。

 even for me， it's a hard task。 I don't want to do it very often。

 And it's even harder to let a computer to program to generate articles， right。

Especially the grammar structure can， and。Can be quite complicated。So really here we will。

 it's unlikely that we will have a model that can really generate documents。 Even here。

 we need to start making simplifying assumptions。And luckily。

 we already have those kind of simplifying assumptions thanks to a long line of research。So。

Probably not need that in a moment so。So we need to make simplifying。Assumptions。

So there's really a long line of work here。 There's the first model called PLSI by Hoffman。

And at the same time by Pau Di Mitll and As。And later。

 there's a famous work called Leton directly Allocation by David Lai Andrew Ning and Mike Jordan。

So and hundreds or maybe1 thousands of papers following all these papers。

 So from this long line of work。Well they are not all focusing on the simplifying assumptions。

But this line of work really identified several important assumptions。

So the first assumption is called the bag of words assumption。

So the back words assumption says in order to learn the sematic structure。

We don't really need to care about the ordering of the words。 So we have an article。呃。

We can just forget of the ordering of the words and throw all the words into a bag and try to learn from that。

So this is a quite reasonable assumption， and you will believe it if you take a few examples。

 So here's New York Times。So if you trust me。I will just randomly promotemute this title for one article。

So like withs， preparations， deal hotels， R， Ebola。So even though I permuted all the words。

 I'm pretty sure you know what this article is talking about。😊，So really。

 the spec of words assumption is quite reasonable。So this is and this is very useful because then when generating the words。

 we don't really need to care about the grammar structure， we just generate them randomly。😊。

And then the next assumption is we said we want to learn thematic structure in particular。

 what are the topics？So what is a topic， So the second assumption is the definition of a topic。

And the topic is defined to be a probabilistic。distributionbution。A probability distribution。

A word it worse。So it says if I know a word comes from a topic， then with some probability。

 this word will be something。 for example， maybe there's a topic called food。

 and if I'm talking about food with say one% probability I will use the word say banana。

That's the idea of the topics under these simplifying assumptions， yes。Yes， condition on the topic。

Yeah， if you know the topics of the words， they are drawn independently and of course arguably this is not exactly true。

 the words will have more complicated correlations。

 but this will capture the first order effect and it's really very useful in practice。呃。So， finally。

 we。Define a topic， and then we want to define what do I mean by a document is talking about a particular topic。

So in this kind of a model， usually document。It's just a n probability distribution。Distribution。

Over topics。呃。So this in particular allows a document to be talking about two different topics or more than two different topics。

For example， maybe 80% of a document is talking about politics and 20% is talking about finance or things like that。

So this is actually a relatively new thing in the earlier works like PR As I every document has only one topic。

But later people find out that。If we allow each document to talk about a probability distribution of topics。

 its， it can fit the empirical data much better。 So that's why people switch into this definition。嗯。

Okay， so under these assumptions。We can try to。So first。

 the most important part of the parameters is for。Topic models is this distribution。

Of topic and words。And they are usually summarized into a topic matrix。

This matrix will be very important in the rest of the lecture， so let's take a closer look。

 So a topic matrix。Will be a matrix that looks like this。Let's say it's an unbiane matrix。So。

 this side is。N and n is actually the size of the vocabulary。

So it could be thousands or tens of thousands or even larger。

So the aside are all the words that are in the dictionary。And this side we have K。

 which is the number of topics。And this number is often much smaller。

 you should think of k as something like 100 or 200， something like that。嗯。

So then every column in this matrix will be a topic。So， column。So are topics。And for example， if。

 let's use the same example， there might be a topic called food。 Of course。

 these names are cannot be automatically generated。 But if there's a topic called food。

Maybe there's a word banana here。And maybe then this entry is 1%。

And this means when a word comes from this topic food， then with 1% probability。

 this word will be banana。And all the entries in this matrix have the same meaning。

And because every column should specify probability distribution over words。

We know entries or entries of this topic matrix should be non negative。And also， columns。

Should sum up to one。Just to make sure that this column represents a probability distribution。嗯。Okay。

 so。So then using this topic matrix， we can try to generate documents。So in all these topic models。

 there's a general。A recipe for generating documents。

So how do you generate a document according to these simplifying assumptions， Well。

 the first step is you。IP the length of the document。And the second step， you pick the。啊，toppics。

For is this document。So topics will be a vector of lens scale。 So W1， W2 to。呃WK。

So these are the probability distribution or topics。

So all the W Is are bigger than0 and some I from 12 K。W， I is equal to one。

So this W specifies what is the。Probability distribution over the topics for this particular document。

And their third step is to generate the word， so for each word。

So say I from one to the length of the document。I first peak。The topic。T I。TI is a number in 12K。

And it is chosen， according to。These ratess WIs。So for each word， say， maybe。

Let's look at an example If W1 is 03，7 and W 2 is 0。3 and all the others are 0。

 then T I will be one will， with probability 70%， and T I will be two otherwise。

So for each word you first truth the topic。And then you pick a word from that topic。Peak word Z。

In one to end， because as we assumed， and it's the size of the vocabulary。

And this is according to the distribution。So that's specified by the T I's column of a。呃。

I will write a dot TI for the TI's column。呃。Okay， so this is the way to generate。The documents。

 according to this topic model。According to many topic models， in fact。

The reason that this is not really a topic model is because there are steps that I didn't tell you。

What distribution you should be choosing from。In these steps。

 I we know what what is the correct distribution to choose from。But first， we did it。

But for this to become a topic model， we need to specify what is how to choose the length of the document。

Lense is not really that important， lens of an article is like 300 words or something like that。

 some integer。And really， you observe that from your data。 So it's really not。

Something that you can optimize for。So many topic models just ignore this length of that document。

Here well also assume it's something fixed and known， so we don't worry about that。

So the difference between all these different topic models from the earliest one and to the much later ones。

Many of them， the difference comes from the step two。So， a difference in。In topic models。

It's mostly in the step two， for example， in the earliest work， P SI。This vector W。

Will just be one of the basis factors。Of course， this happens with probability。呃PI。So in these works。

 they are assuming all the documents are about a single topic。

So this topic proportion vector is really a basis vector。

 meaning it's only one in particular entry and 0 everywhere else。

And the whole document will be about this single topic。In the later models， for example。

 this latent directly allocation。The vector W is chosen according to something called a directly distribution。

With some other apparentin alpha。So the reason they choose this distribution has to do with simplifying their algorithm。

But really， the main intuition is this is a distribution that do not just generate all these basis factors。

 So it allows。A document to talk about more than one topic， but at the same time。

 this distribution tend to generate sparse vectors。Which translates into a topic modeling language。

 It means this every document is only talking about a few topics。

Which agrees with our intuition because we don't expect there' is a document talking about。

 say all the 100 topics that we are going to find。And there are many later models。

 and they all have different ways of choosing the distributions。嗯。In this lecture。

 we will ignore all these differences。We will treat essentially treat all these Ws also as a part of the。

parametersmeterters。嗯。So they can be arbitrary as long as they satisfy some reasonable assumptions that we are going to make。

And also， we are not going to be able to handle the。

Most general algorithm for learning topic model instead will be focusing on easy case。E case is when。

When n goes to infinity。Remember， this n is the length of the document。

So the easy case is if every document is really very， very long。Of course。

 Ar is not very reasonable in practice， but。For this lecture。

 let's focus on this simple case and if you want to look at the case for a finite n or a small N。

 there are relevant papers about that。So it's a good thing when this number this length of the document goes to almost infinity。

Is that we can hope that every word appears more than just once in the document。

And that allows us to estimate all these all these probabilities。So， we can estimate。

So probabilities。Of a word VI。Being a particular word V。

Conditioned on this word as chosen from this document。So to estimate this。

 we just take look at the document， look at。How many times this word appeared divided by the length of the document。

 and if the document is 3 long， this will be a fairly good estimate for this probability。Of course。

 for it to be accurate， the document， the lens need to be comparable to the size of the vocabulary。

 which means it's a really long document。But for now， let's work with that。for now。

 suppose we have these estimations。 We know what is the probability that a word appears in this document。

So what does that tell us well？So once we have all these probabilities。

 we can organize all these probabilities。In the matrix。And this will be a document。AWord matrix。

On this side， the dimension is and number of words in vocabulary。And on this side， the lens is say。

 we have M documents。And every column will be document。

 it will specify this probability distribution， what is the probability that we choose that we see this word if we are in this particular document。

And that's really roughly all the information we've got because we are assuming bag of words assumption。

So really the words the ordering of the words do not really matter。

So how do we deal with this matrix well。We can observe that。According to this generating process。

We have for a particular way of generating words。So according to this process。

 what is the probability that we generate this word in this document？Well， according to here。

 it goes in two steps， right， you first choose a topic and then you choose the word according to the topic。

呃。So this is equal to。Some overall topics。Say J is from one to okay。

The probability is that this document generates this particular topic。So， T I is equal to J。

Condition on the document。Times。The probability is that。Once I have this topic。

 what is the probability that I generate the particular word？So Z is equal to V。Conditioned on T。

 I is equal to J。So this is just an equation that's true because of probability。嗯。And really。

 what is this。These are really just the the topic probability distributions。

 these W values that we have here。So these are really the W values。 And what are these values。 Well。

 these are really。What we have in the topic matrix， right？So this is 3D A of。Are we J。

So every entry in this matrix is the sum of product of these things。

And we can write this equation much more compact using the rule of matrix product。

So this is really equal to the matrix a。Let's call this matrix M。Ats 3D。

 you quote to is a matrix A times。A matrix stopped him。Where A is just our topic matrix。

And a column in W would be the W I for the。Documents。And of course， A has the N by K。

 and W has the K by N。呃。So if you think about it， this， this is really equivalent to this formula。

 because。This particular entry。In the matrix product is equal to the inner product of this row and this column。

 this row correspond to all these values， and this column correspond to all these values。呃。

So this is very good because it relates。Document word matrix， which we know from the data。

To the topic matrix， which is the parameter we want to learn。So really。

 our problem becomes given this matrix A， sorry， given this matrix M。

 I want to find this decomposition a times W。Your A and W have sides much smaller than M。

 So that's a important structure in this matrix。And that is actually a problem called non negative。

Mattrix factorization。可。Factorization。That's studied independently of topic models。嗯。

So a nonactive matrix factorization problem is just given。A matrix M。It's N by M。嗯。

The goal is to find。Marices。ANW。Well， A is in R to the M by K。NW S in R to Z。K by M。呃。With。

Non negative interests。嗯。And。is equal to8 times something。

So the reason we want non negative entries is because， of course， I as we explained。

 this matrix A is the topic matrix。 The interests are probabilities， so it must be non negative。

Similar things works for AW。There's also the normalization constraint， but actually。

 that's without loss of generality。 as long as M satisfies the normalization， we can always。

 without loss of generality， make A And W satisfy the same normalization， so。So。

 so that's not a big problem。 The big problem is really， is this non activity constraint。

If we don't have this constraint， just， we want to factorize a matrix M into two smaller matrices。

 That's a very common problem。 That's just rank decomposition。 We can just pick K to be the。

K looks strange。 we can just pick K to be the rank of the matrix。

 and there's always such a factorization。And usually we can find such a factorization by doing singular value decomposition。

But really， those decompositions do not make sure that A AndW have non active entries。

And an activity is really important in our problems。

 otherwise we cannot interpret these parameters as the probabilities。So really。

 we want the non activity。 but unfortunately， like many times we see in machine learning。

This problem is known to be MP hard， shown by a web basis。Okay， so now we have an MP hard problem。

 we just talked about several ways of getting around MP hardness。😊，So， here， in particular。

We are already in the average case in some sense， because we came to this problem from topic modeling。

So we also don't want to do any approximation in this case， so。In this case。

 we can actually identify some。Natural assumptions， in particular。

 this matrix A is the matrix of topics and words。 So we would think that we know enough about topics to have some special properties。

 It turns out one of the properties that。People are defined。

In a different context called separability， as defined in a work bydonnaho。And Sden。呃。

Its very relevant in the topic modeling case。 I's foresee the definition。So。

The definition of separability says matrix a。A is in R n by K。Is separable？If。For any column。I。

I in 1，2， k。There is a role。Say AI in。So that set how rows。Such that。First。

The intersection of this row， and this column is。Bigger than zero。But hand。呃这 is。

So other interest in this show。Are all zero。For all。Okay not take control。呃。

So this is quite abstract let me draw a picture too。呃。Explain so what is this definition saying。

 it says this matrix A is separable if for every column。For every column I。

 there should be a row thats let say it's this row。That's called A sub I。

And what property does this row have， Well， at first， this particular entry。Should be long劲哦。

And then all the other entries in this row should be 0。 So should look like this。Right。Similarly。

 for another column。There is a different row。And this particular entry is non active or is positive。

And all the other entries are zeros。So in other words。

 actually we promoteute the rows to make all these rows up in the front。

This matrix actually looks like。Serious diagonal matrix。On top。That's formed by allies。Roose。

And what you can have anything at the bottom doesn't matter。

So this is what separability means for a matrix。And what does mean if we assume the topic matrix to be separable？

嗯。So。So we can translate this assumption in the context of topic modeling。So。

 so it says for any column， but a column is a topic。 So it says for any topic。

And then there should exists a row， but a row is a word。So there is a word。

And that we will call anchor word later。And what should this word。

 what property should this word have， Well， it should have a nonze entry here。

 which means it has a nonze probability of appearing in this particular topic。

And then all the other entries are zeros， which means this word just does not appear in any other topic。

So this word that。So sp should only appear。In this topic。For example。

 if we are talking about weather， maybe say a word like snow will have some large probability in weather。

 but。Quite unlikely in other topics。 or if you think no it's not specific enough if you are like。

Polar vortex or some things like that that are really specific to weather。😊，嗯。

So hopefully these anchor words exist for all the topics。

 and that is our assumption on the topic matrix。诶。So is there any question。嗯。So intuitively。

 this assumption should help in。In learning a topic model， because。

So first notice that it doesn't mean if。A word has a topic， the anchor word has to appear。

Because maybe the document is short and it just didn't mention the anchor word。

But what we can really say is if we see the anchor words in a particular document。Then that document。

 at least some fraction of the document， must be talking about this particular topic。

And that could be something very useful。And here we let's look at that picture again。

 we have this matrix M is equal to8 times w。So what happens if we have a matrix A that's separable？

Again， let me draw this picture here。 So M is equal to。He time w。

But now we are assuming a is separable。So in particular， the R these rows。

 the R these rows that say there is one row where only the first entry is non active。

So then what is the product of this row and this matrix。Well， the product is really just。

A role in this M matrix。And this row in the M matrix is really。

Very similar to this first row in the W matrix。Right， so basically。The observations。

The AI is role of M。So minus AI throw as a vector is equal to。呃。For the corresponding entry。A aI i。

Times。The eyes roll of W， right。So in words， the rows of W are really appearing in rows of M up to scaling。

So that's got to be very helpful because we want to know this product A andW。

 but W is actually hiding in M。Another observation is even if I have a row。

 that's not really a row correspond to an anchor word has many entries。Still， I can write MJ。

 this row in M。As a combination。So it's equal to some I from1 to K。系。Zhenke。Oh， sorry， J I。WY。

So even for rows that do not correspond to rows in W。

There are still non negative linear combinations of rows in W。Right。And actually。

 without loss of generality。呃。We can scale。Can rescale。M。So， that。Ros of。M AW。All sum up to one。呃。

So we can really rescale the rows of M to make sure they sum up to1。

 And then there's a scatter of A AndW so that their rows also sum up to one。In that case， this guy。

 because it's only non0 entry， will be really1。 So M A is really equal to W。And this。

Instead of just a nonactive combination will be a Comx combination。So really。

 the rows of M are either really the rows of W or they are in the Com hall of the rows of W。

So in this way， we have reduced the problem into a geometric problem。呃。

So what is the geometric problem， Well， in this problem， we are given。And points。V1， B2。

VN in R to ZM。That are in the Comx hall。Of。V， A1， V A2。 remember。

 these are just the same as rows in W， right。To V AK。We're a 1，2， aK。Are in1。But， they are unknown。

We want to find。A1，2， A k。Or just the corresponding row screw enough。We want to find V A1 to V AK。

So in picture， it is equal to it is this kind of problem。 We are given this bunch of points。

Sa are really in the comic small in this triangle。And the points we are given include all these three vertices of the triangle。

And our goal is to redefine all these vertices。So this problem is really equivalent to finding the non negative matrix factorization。

 which was here。It's equivalent to the nonactive matrix factorization problem。

When we assume the separability assumption。Now this problem becomes much easier in the rest five minutes I'm going to give you an algorithm for this problem。

呃。So first notice that it is possible that the rows of w， which correspond to these verrtices。

 it could be that there is a row of w that's lying inside the convex hall without any further assumption。

But that's really a degenerate case， because in that case。I can have the same factorization。

 but removing this particular row in W。 And that will result in a smaller factorization。

So in some sense， that's a degenerate case。 and we。It's like the matrix has rank R。

 but I factorize it into a matrix with r plus1 columns and that's not something that we want to do。

 so we will just assume that the rows of w are not inside the Com hall。

 they are all vertices of the comicx hall。So how do we find the veres well。呃。The algorithm。

Is just to check。Whether。A point。Is in the Comax Hall。Of。We 1，2， V， I1。 So all the other points。

So of course， we first removed the duplicated points。So， the claim is。If。The eye is。Is a vertex。Then。

 then VI is not in the Comx hall。And if V I is。Not a verortex。Then we I must be in this comicshu。

Right， because。But this is kind of clear the proof is very easy if I have a point here。

 that's not in the Com hall， I remove all the duplications which doesn't do anything here。

 it's still in the Comx hall of these three points。But if I remove this one。Then， of course。

 the Comx hall looks like this and it's not in the Comx hall anymore。

And how can we check whether a point is in the complexx hall of some other points？

So this can easily be done using a linear program。 Basically。

 what does it mean for V I to be in the economic X hall。

 It means V I can be written as some J not equal could do I。Alpha J V J。

And these alpha Js are co combinations。 So alpha Js are non0 and some J not equal to I。

Alpha J should be ones or one。So this is the near program。If this linear program is feasible。

 it means VI is in the Comx hall。Of。All the other points。

 and therefore it must be something that's inside。If this linear program is not feasible。

Then it means VI cannot be represented by the con combination of other points。

 and that means it must be。At this point here were one of the weretices。

So that's a very simple algorithm。But in order to apply it to the topic modeling。

 there are some more complicated things that we need to worry。So first is。

 we cannot really estimate all these probabilities accurately。In fact， it's very far from accurate。

 but even if it's a small perturbation。This if， at these points can move。

 especially they can move in a higher dimensional space， meaning they can move outside the board。

Then it's no longer true that something can be in the convex of all these points。 they might not。

Really be in a lower dimensional space anymore。呃。So in that case。

 we need a slightly different algorithm。 In particular。

 we need to check whether the point is close to the Com of other points。

That's still the inner program， but slightly harder。And finally， we cannot really estimate M。

Well enough， instead， we will actually estimate what is the probability that two words appear in the same document。

 And that's something that we can estimate as accurate as we want once we have enough number of documents。

呃。Yeah， so， so this is idea of how we design algorithms for learning topic models。

 What are some difficult problems and how can we use。

These kind of natural assumptions to get around the NP hardness result。

And it turns out this algorithm， not this particular algorithm。

 but the improved version can actually be implemented。 It's pretty fast。 and it works for， say。

 New York Times article corpus， and it it has resources that's comparable to all the previous heuristic algorithms and it's even faster。

So if you want to know more about it， I have a few paper science this and you can email me or I can tell Glani。

 where are the papers。As that's it for today's class， Thanks for coming。

