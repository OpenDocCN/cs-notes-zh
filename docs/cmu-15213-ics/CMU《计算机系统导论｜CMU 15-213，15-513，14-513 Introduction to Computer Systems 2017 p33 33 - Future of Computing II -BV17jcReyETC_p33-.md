# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p33 33 - Future of Computing II -BV17jcReyETC_p33-

So this welcome to the last lecture of the semester in this class。So in continuing our theme of。

Sort of what's？In the future and what's kind of the late breaking。

 what's kind of hot now in terms of what's going on in computing， wanted to follow up on。

Some of the stuff that Raan talked about last night in terms of the。The way that。

Large scale machine learning。Particular deep networks has really started to dominate。

The computing cycles in say in the cloud and so forth and in data centers。

 and this is a recent phenomenon of the last。あ。think it's around five years。

That where we've seen these deep neural networks have。

Good success at things like machine translation， object recognition， video， activity recognition。

 things like that。And face recognition。And。All the services that these can provide for， say。

 your smartphones and so forth。Okay。And so what this lecture is going to talk about is research that my group has done over the last few years looking at some of the issues around big learning and in particular。

 looking at，Big learning is my shorthand for large scale machine learning。In particular。

 looking at sort of asking the question what's so special about this computation that makes it distinctive from other things we've looked at over the decades。

And how can we take advantage of？That those distinctive properties。

To build better computing systems in support of these types of computations。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_1.png)

可以。So。So the topic is what's this special about big learning？

But I thought it'd start with a simpler question， which what's so special about big data？

A lot of people have heard a lot about big data in the last decade or so。

And so I went to the all knowing source， Google。And I typed it in。And I got directed to this video。

I'm not sure why this particular video， but big data， big phenomenon， big hype， and also big value。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_3.png)

Okay。But we're going to just focus within the whole space of big data on machine learning over big data and some example kinds of things were that fall under this class of applications includes things like recommendation systems。

 okay that tell you maybe because you like this kind of movie。

 maybe you want to watch this kind of movie or like this book maybe you want to watch this book and that's called a collaborative filtering。

Another class of problems is called topic modeling。

 this is where you take a sort of say collection of news articles and you want to cluster them into clusters based on the words that are in them。

And in this particular case， you specify how many topics。

 like maybe I want to take the New York Times articles and classify them into hundred of topics。

 but you don't say what the topics are， you let the system try to figure out what the best0 topics are。

There's all sorts of。Classification problems that can be modeled as regression problems。

In particular， often multiial multiclass regression problems。And then there's these deep networks。

 these coal networks that we talked about a little bit in the last class。可以。

But also what will fit under this style of computation that we're going to talk about are other types of iterative data analytics like computing page ranks。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_5.png)

Of webpage。Okay， and we're going to have a systems computing systems perspective on this topic。

And so the goal from computing systems perspective is to say， you know， can we have a framework？

That allows you to express the kinds of computations you want to do。As say。

 a machine learning expert。And。So that that it's easy to use， easy to program。

 but also delivers good performance on both large and small clusters。可以。

And we're going to revisit some of the examples just really briefly slide or to each that were mentioned in the last lecture just to bring you back up to speed。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_7.png)

Okay， so Hadoop。Is fundamentally a distributedtribut file system？

That also comes with a resource scheduler。And it's a way of easily mapping。Computation。

 large big data computation across a whole bunch of machines using a map reduced style of computation that was talked about in the last lecture。

So here's a diagram that shows that you have the different nodes in the system here。

 there's three and  two three， and there's a bunch of input data on each of the nodes。

And they first perform the map of the map produce， whatever function you provided for the map。

 and that creates intermediate data。That's still local。

 and then there's this exchange of all the information so that the light data ends up。

Within the same node。And then on that like data， you do a second function。

 a reduced function that's provided by the user。To produce a final output。可以。

And this was a very successful approach starting about 2006。

open source software and a lot of sort of what I would describe rudimentary big data analysis problems can fit into this framework and it became very successful because of the ease of use okay。

And not because it delivered any kind of reasonable performance。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_9.png)

GraphL was also mentioned by Randy in the last lecture this is came out of CMU。

One of the things that it introduced was instead of this map and reduced framework was to think of computations on graphs as computations relying as occurring on graphs where there are nodes and there are edges。

And the nodes have properties and the edges have properties， and you can update either of those。

And then a computation is expressed in this， think like a vertex。

Framework that actually originally Google's Pragel introduced where you say， oh。

 from the viewpoint of this is one node， what I want to do is some computation based on my neighbors。

And there are values and the weights on their edges。Okay。

And so that's a different style of programming that fits quite nicely in certain types of computations for just like page rank where you look at your neighboring pages。

 the ranks of your neighboring pages， and you update your own rank based on those ranks。可以。🤧嗯。

And so the key thing that made this take off was that this graph parallelil abstraction。

 distinct like a vertex abstraction， which actually， again。

 quite easy to use for a particular style of computation， much easier use than mapreduce。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_11.png)

And so that's why it took off the other reason it took off is its performance was significantly better。

 here's an early result on Triangle count which is sort of how many friends of friends are two of your usage friends also friends。

And this is saying that on Hadoop， something that ran on 1，500 machines and took。

 or was that seven hours could run on 64 machines in a minute and a half， okay。

 so it was significantly faster。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_13.png)

Okay。And then so that was the original GraLb， the GraphLb too said， well。

 the problem with this thing like a vertex way of doing things is that if you have a very popular node so a person with a lot of followers right。

 Twitter followers for instance， then that computation that one vertex does can can take much longer than the w restt of us right？

And so the notion there was that you would take high degree vertices and you would actually split them up into subvertices enough so that there was kind of overall there was lower degree and then you applied this sort of。

Gather， accumulate， scatter process where within each of these。Partitions of this node。

 you would do whatever think like a vertex computation you need it。And then， all the。

Sort of replicates， the place， you， the stand ins for that node across the different machines would communicate and produce the proper value。

 and then there'd be a scatter where it gets broadcast back out to all the respective nodes that needed to hear。

And that turned out to be a very effective way of dealing with high degree nodes。

The other thing that came out of this project was something called Graphci， and this was saying。

 okay， we've looked at running these big data problems on 1500 machines as Saoop was doing on a 64 64 machines。

Or whatever the number was to your effort I' gotten 64 machines。

 but what if you just have one machine， you know， what if it's just you and you don't have a cluster。

At your disposal and you don't want to necessarily pay Amazon to rent cloud resources。

Amazon or Microsoft or Google， any of those。So what this did was to say， well。

 can I redesign the way I process these machine learning algorithms such that they have good performance even if they have to scan through SSDs as they're going along and that was actually quite successful because for instance。

 this is showing the performance on a single Mac mini so on one machine where the data is sitting out there on an SSD has almost as good performance as this 10 node Hadoop installation。

Right and so that enabled。You know， sort of revealed that you could do this fast， big learning。

 even on a machine， relatively fast， it's not going to be get as fast as other。

 but it's so reasonably fast on a machine， a single machine where you had data residing on SSD。Okay。

 our disc。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_15.png)

Okay。And then finally， Spark came along and actually about the same time as I guess a couple years after GraphLb。

 and this was to address this issue of why is Hadoop running so darn slow？Okay。

 and so Hadoop was running so darn slow because among other things。

 it was writing out the disk and reading from disk after every single map and reduce map reduces stage。

 right， So you quite have multiple map reduces。 You're writing out and reading from disk。

And they were doing that because that was the only way that they knew to make sure that you didn't lose all your work if your machine crashed and your sheets crashed。

 okay so the way you need to get a cheap persistence was to have the right in and out of desk。

So instead， what the Spark folks figured out is that there's other ways to get persistence， right。

 other ways to get duability， and the way they proposed was they said， look。

 you know these computations tend to be sort of large。Operations that are done in some sort of。

You know， the data folk graph kind of well。And so if we restrict ourselves。

 if we allow ourselves to operate in memory， but restrict ourselves to these operations that are effectively deterministic transformations on their inputs。

😔，every time you ran this map on this particular input， you'd get the same result。

 then I just have to keep track of this flow here。系い。

Keep track of this little graph of how things happen。 and then， for instance。

 if this machine goes down or the machine this design goes down， then I just rerun this piece。

 but these pieces are still fine right and I can rerun from there。

So by thinking in terms of a lineage of operations and only recomputing those that actually were affected by the crash。

 then you could have fast recovery times and yet operate entirely in memory。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_17.png)

Okay。🤧咳。And。The other thing that's kind of interesting about this sparkark project。

 this is out of Berkeley， was how fast the community responded to this breakthrough， okay？Basically。

 you know they had the research ideas in 2009， they released the first code open source in 2011。

 it got into an official Apache incubator status， which is kind of official blessing of the open source community that a lot of people are going to work on it。

And by 2014， it was in all major Hadoop releases， so all these companies that were releasing things on top of Hadoop or were using Hadoop in their work were now using Spark just a handful years after they first came up with the idea。

可以。嗯。And then and sort of as as a map， roadm with how this gets done， the key ideas that have， well。

 first have something that's。A significant enough improvement that people want to do it right so they said look you can still use Hadoop style of programming we're just going to make it you know towards act faster Okay so that was enough to get people to pay attention The second thing was that they continued this pipeline of research innovation right that they continued to come up with new ways to improve their system so it stayed ahead of of the you know of the competing。

Deeing efforts， right？And then they also， you know， as not surprisingly forked off a startup because。

 you know， university， you know， students don't necessarily write production quality code。

 it's not maybe in their you their best interests in terms of they'd rather get。

 know their Ph published or whatever a the dissertation finished。But if you have a startup。

 then you can。You know， pay people basically to make the hardened to code， make the code good。嗯。

And then working with these industrial partners that hop on board。

Because industrial partners like the fact it's open source。

 that means that they can work on it and all their customers can use it， like Intel， for instance。

 would say， the more that this good stuff is out there。

 the more people are going to want to buy our processors。

 right because they've got more applications that they can run on。可以。

So that should be encouraging to all of you as you you know， in whatever you do in your。You know。

 goinging forward after you finish you know， well， maybe in your senior project on。

 right that it's no longer takes that the barriers for entry for having impact probably have never been lower。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_19.png)

In the computing systems and software areas。Okay。All right。

 so that's kind of the context for which the work I'm going to talk about was started。啊。

So in contrast to the system I just described。We decided that they were。

 they were always being agnostic to the。The characteristics of the computations that that were trying to be solve。

 okay， and so our idea was that we were going to try to discover you know what's distinct。

 what's so special about these big learning in particular the training algorithms because those are the ones。

As just touched on last lecture are the algorithms that take the days and weeks and months and so forth to run。

 So what's special about those algorithms that we can actually do smarter things than were currently done before。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_21.png)

Okay。Any questions so far？对啊。I do graph lab， sparkar。そまに。O。嗯。

So to think about what's especially about big learning from a As perspective。

 it's important to first look at it from a mathematical perspective。

 what are these computations trying to do？Okay， the key component of these computations are that。

You're trying to fit a model to some data。 because if you can fit the model to some training data。

 then the assumption is when you get real data or testing data it'll be also be good at predicting the real data。

So you're given a bunch of training data。And this is labeled data。

And then you're given some sort of model。Which is just a。You know。

 basically some sort of mathematical expression， system of equations and things like that。

 such that the model has parameters to it right there's values。

 I mean you can think about like a regression right， the simples thing is the linear regression here。

 you've got a bunch of points and you want to draw the line that through it。

 the points that minimize the ear。 So the model says it's got to be a line and the parameter says well。

 what's the slope of this line。So that's like the simplest possible thing。

 and then there's some objective function。Okay， they're either trying to minimize or maximize。

 like the objective function for linear regression is often something like minimizing the， the error。

 which is sort of the。嗯。knowThe distance from each point to this line sum are all the points right or the squared errors of that if it's a classification problem and you're trying to have a bunch of points and you're trying to break them into two groups based on a classification line。

 it's maybe the number of misclassified items you're trying to minimize。Okay。

 now the issue about these things in general is that unlike the lit regression case。

 there's no closed form solution， so instead the algorithms are iterative。

 they go through and they look at the training data， they compare it against the model。

 they see where what frames，Can be not。In the direction that will help that training data。

 make the training data， make the model better fit the training data。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_23.png)

And these types of problems are solved using any of many possible variants of stochastic gradienting decent。

Okay so what this picture， so if you think about stochastic gradient descent。

 its there optimization function across the choice of parameters。

 this is a simple case where there's just the you know two directions of parameters right。

 two choices for the parameters tells you for each of those combinations what is the value of the objective function。

 and in this case we're trying to minimize the objective function so we're making our way from say some initial solution。

D。This slope to this minimum and we're doing it a series of iterative steps where at each step we'reging the training data。

 nudging the parameters to make the fit better。那款始上了。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_25.png)

O。So。So this is a slide from last time， right which was emphasizing the fact that， well。

 first that these are iterative numerical algorithms。

That if you grow the model size linearly and also grow the training data linearly。

 then the training effort goes up quadraically。So that's one of the reasons these things could take。

 10 days and so forth。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_27.png)

Okay。So。So what's so special about this computation I just described。 Well， first。

 let's talk about the bad news。 Okay， the bad news is that there's lots of computation and lots of memory。

Needed， okay， you do many iterations。The training times going you many variations over this data。

And these models are big， right and kind of the product of those two things。

 there's lots of parameters in the model。And because of that for these really large models。

 youre actually， I'm going to talked about。What you do on a single machine want you to do on maybe a large shared memory box。

 but for a lot of these models， they're just so big that you need to distribute them across a bunch of machines。

 you're going to need to run them in the cloud， run them in your data center。Okay。

 so that has some costs， right， the communication costs and synchronization costs。Across nodes。

 different nodes in a data center is much higher than， say within a single machine。

 between the cores of the shark machines。Shark machines。嗯。So。

So the fact you have to split up your computation widely。Would not be such an issue if。

Once you split it up， they kind of you know didn't have to talk to each other they kind of just work for a while。

 solve the problem， sent the solutions back and they'd be done。

 but unfortunately the way these models work there's a lot of interconnection between the parameters and how they impact one another and so it's not really one of these nice partable cases you're going to divide this up and there's going to be a lot of demand for communication synization。

And that combination means that the training is very slow， it's hours， it days， to weeks。

 even on many machines。Okay。And so that's the bad news， but bad news for。

Researchers is always good news。I mean， if we no problems or challenges or issues。

 then we would out a job。So， you know this is just saying why pre assistance research is needed。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_29.png)

Okay， glass half floor， right？Good， so this is an example from a paper。Out of CBU。

 the appeared in OSDI 14， that just gives you an example， at least even back then。

 which has been three years ago now， how big these models were。So you can see that at the high end。

 the model size are 100 billion parameters。And they can be run on 100，000 corps。Okay。

 so these things can be really big and then here's the atom one that Randy talked about last time。

So it's not even the biggest， even back in 2014， it wasn't even the biggest and things have only gotten bigger。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_31.png)

Okay。Lots of communication， lots of synchronization， so particularly。

If you do things in Hadoop or Spark。There you're in this map， reduce this sort of bulk synchronous。

Frame and this is the picture from the last raised slides and was was talking about what are the difficulties of book seeks？

So。Let me remind you， so in bulk signals， so this is the different processors。In bulk synchronous。

 you have， each of them do their local compute。And then they have to synchronize。

And then they do all the communication， so they exchange all the updates and then that repeats， okay。

And so。There's a couple of problems with that。 One is the exchange。

All the updates are exchanged at the end of each it ratio。

There's no overlap between communication and computation。if you use this particular button。

So it means your communication。Between these machine your communication network is。You know， I don't。

And then all of a sudden boom is really bursty， right， and so it can be a bottleneck。

And the second thing that was also highlighted in the last lecture is that you only made progress at the rate of the slowest。

Okay， at every single step。 Okay， so that's what this picture is showing。

 the slowest may change from P2 to P4 P3 in this example。

 but you're always stuck waiting for the slowest。 Okay， so you can imagine when you have 100000。

Of these nodes。That there's always going to be one that's， you know。

 several orders magnitudes slower than all the others， right， And so you know that's the rate going。

And that's called the Stragggler problem。In in literature。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_33.png)

Okay。So any questions on the bad news？Good all right， so here's the good news。So。The way that is。

These training albums work。Is that there？They each worker， each machine。

Each worker threat on a machine has some training data。

 it looks at that piece of training data and it reads the model parameters that are relevant to that training data and then it as I mentioned sort of nudges it in the direction wants to go and what I really mean by that is that it provides a delta it says that add one to this one or so track 。

5 from this one。It doesn't say that the new value should be7。😔，Okay。

And because it's always these deltas。Then the updates are actually what we of discussion。

Okay ignoring flood point issues， which are fine we in this case because again。

 we're just working our way down this。This convex intensity convex slope。

 and so 4 point errors are not going to deter us from getting there。ok。

The other thing that's interesting to think about is that， I drew this picture of the slope。Okay。

 and。You know， it's it's。You could take the most direct route if you wanted to。And you get there。

All right， but you can also take a more you know less direct route you look at it， right？

It's like you're skiing down this thing right so you're going to get to the bottom either way。

And it's just a question of how many back and forth does it take to get to the bottom？😔，Okay。

 did you go like just full barrel down the slope？knowAs fast as you get there。

 or did you take your time a little bit， go back and forth like that， okay？嗯。

And what that translates into from an assistance perspective is that there's actually a。You do not。

 unlike， say， a general distributed computation， like some big。

 large simulation or something scientific simulation where you really need the exact values。You。

You don't need to tightly synchronize the updates of these frame。😡，There's a natural tolerance。

For lazy consistency of the parameters。Okay。嗯。If I'm using steel values。😡。

when I'm reading the parameters， that's okay。And there's a bunch of others okay that we've identified。

 and that as time permit， I will cover some subset of them。Okay。

And the point is that because of this good news， we can overcome some of the performance。😔。

Challenges of the bad news and make the whole thing run orders the magnitude faster than it otherwise would。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_35.png)

可以。2。So。Both in the last lecture， this one， we talked about。You know， programming abstractions。

 programming frameworks that are used in。In various of these large scale computations。

And I mentioned map Red， I mentioned graph parallel， think like a vertex。

 here's the one that sort of we invented here at CMU called the parameter circle。Okay。

 so the parameter server is a distributed shared memory programming style。And in this style。

 what the workers do so if you have a worker that's got this training data。It。

Thinks of the set of parameters as being stored in some sheer memory。

And which just allows it to read it and update it。Okay， so for instance。

If your code on a single machine looked like this where you read the old value of a variable。

You applied some function just figure out how you wanted to change that variable。

 and then you added that delta。Back to the variable。Okay。

 if this is what your code looked like if you're just running it on， say a single shark machine。

It's identical， right， it looks just like before， except we wrap these reads and writes。

 so this parameterer server read。And parameters of increment or update。Okay。And so therefore。

 the way you write your code， even though again as it crosses all these nodes。

 is very natural style for anybody who's used to writing。As a single machine peril。On aing machine。

And moreover。ええ？You can write it like the mathematical formulas in which they often are defined right the steps of these machine learning algorithms are often defined mathematically and。

You don't have to do any translation to other formats。

 so you can just sort of write your code to exactly capture the mathematical。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_37.png)

は。🤧嗯。🤧Okay， so that's the property model。But we still don't want to have this bulk synchrony issue。

 right？So。One thing you can imagine。Okay， is that the？嗯。

I've said you don't have to take the steepest path down this thing you can sort of zig your way down and therefore there's a tolerance for less consistency。

Relic to see。So one of course the people would looked at is they say， well， if this is true。

 then why don't I just remove all the synronization altogether？Okay。

 well I just run this thing with no synchronization at all， so fully asynronous。

Sound like a great idea。OkayBut what happens is that the。

That they sort of the whole process diverges。Instead of going down the slope at all。

 you end off shooting off a cliff。Okay， it's。And that's what happens in practice that things tend to go just。

 you know they go nuts， they don't converge at all， you just run them and want and run them。

 and also there's no longer any convergence guarantees。

 most of the algorithms have a number of the algorithms have some sort of convergence guarantees。

Just to assure you that no matter what happens。Along the way， things are going to converge。

 certainly the bookynchronous ones have that feature。

But the fullyieryners don't have any to so you don't get the comfort of knowing the algorithm is going to converge。

 and in fact， it often doesn't converge。A lot of ski accents。Using that。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_39.png)

O。So instead， what we proposed was something that's in between those two extremes。

What we said was that。We're going allow。I have this notion of a staless bound。

 in this case it's S equals3 in this picture。And what that says is that the fastest and the slowest threats。

Can drift apart by most e iterations， and we're okay。哎。

But if you ever get more than if you ever have a thread。

 it gets more than three iterations ahead of the slowest thread。Then in that case。

 this thread needs to wait。Or this thread needs to catch up， right， read something。

Read the latest value and get caught up。And so。What's interesting about this is that。

 I mean at the least it saves you a factor vest in my communication and synization。

Because you' you're saying well， only have to worry about this every S steps。

 and're finally have to communicate once every S step and so forth。

 but it's actually better than that， okay， if you think about this。

 if this is think about the analogy to a really tight horse race。一。And a really tight horse race。

There's at any point in time， there's like a leader and there's some horses the trailing the leader and the horses the trailing are going back and forth and maybe not to the final home stretch that the leader finally wins。

 right？But if it's a tight horse race throughout the entire race。

 the fastest horse never got ahead and the slowest horse by more than some， say， fixed amount， right？

And so what could happen， same thing can happen in this case here。

 right we can go the entire computation。Without being forced to awake。Okay。

 if the horse race stays tight。Okay， does that make sense。Any questions上来？Right。

And so the protocol is that you're keeping a local cache of parameter values and fors。And it goes to。

 wants to read a Brammar， it looks in the couch。And if the cash， the entry of the cash is。

Is stamped with the iteration number and it looks and says， oh， well。

 there's you know this is too stale this is not if it's more if the gap is more than this。

 it's too stale， you go and read the latest version from the network。

 otherwise you can just use that cache version。Without any coordination。

So the choice of that is really sort of a stale in the sweet spot。

So this exploits both the community of associated updates and the tolerance for lazy consistency。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_41.png)

And the sweet spot arises because。啊。だら。So I guess my steaming analogy breaks down。

 so what's happening is that the shortest distance down this slope。O。😊。

It's the one that requires you to synchronize all the time。Okay。

So you're making the system as a whole is making really good progress on every step。

But it's being held by the str at every step so it's actually you know the most direct path is the slow path right it's the one that's taking the fewer steps。

 but each step is really slow。And so that's what this is showing here。 So this is if you。

 if you don't。嗯。If you just do bulk synchronous， then the。

And this is sort of how much time it takes to do， how much work so higher is better in the scrap。

 this says you're basically every iteration is going slower。Okay， all each generation。

Is much slower than the ones that have。Le like okay and in fact。

 the fastest iterations from just iteration standpoint is the one that's fully asynchronous。

In this case， you're saying slacklack is infinite。So that's the ones that's making the most。

 the iterations are just blazed by because no one's synchronizing。

 here the iterations are crawling along because you're having to synchronize every time。

But on the other hand， as mentioned， if you're synchronizing all the time。

 then the effectiveness of the iteration。how much progress you're making towards the objective function。

I the best of the choices。Okay。So you're having to take fewer steps to get down the slope because you're taking the most direct path。

 but each step is slower and conversely the fully asynchronous one in this case。

It looks like it did converge， but it's making the least amount of progress。Per information。

And so when you combine those two competing factors。

 you find that something in the middle like a slack of three in this particular。Application。

Get you the best results。Okay。那 questions上来？Yes， what's the WPC。Yeah。

 didn't that's work per clock it's basically。We ran further experiments where you did more。

A relatively large amount of work between for each step。but the results are。Pretty much the same。

Yeah， these are graph from paper， so that's why they have。WPC that we didn't。

It's not needed for the purposes of this section。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_43.png)

O的。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_45.png)

So the next thing I want to talk about is this repeated parameter data access pattern。

And I'm going to use the example of Pat to illustrate this。All right。

So here you have three pages and you have you know this。Page refers to this page and so forth。

And so the algorithm is very simple。 You initialize the ranks to some random values。

And then you repeat this loop until you reach some notion of convergence。For each link from I to J。

 you read your rank and you use that to update the rank of the neighbor so you read the rank this link goes from here to here。

 you read the current rank of this and you use that to update the current rank of this right so if this one is popular for instance that may increase the rank or the popularity of this one。

All right， so now given the processing is all about the edges or the links。

 you take all those links and you divide them among all the workers。

 and in this a simple example we just have two workers， worker zero takes links zero and1。

So from worker zero perspective， that exact same loop means it's going to do the following first link zero。

 who wants to read the rank of page two and use that to update the rank of page zero。

And then it wants to read the rank of page one and update the rank of page two。

And then it's done with that all its edges。Okay。So the point is that the， I mean。

 clearly the value of how this gets updated。It dependspens on the actual values of the re。

But the access pattern did not， the access pattern is the same every time you read this。

 you update that， you read this， you update that。Okay， from a computing system standpoint。This is。

The idealla pattern， one is' completely predictive。

So even though it' it's just this graph all over the place who knows what。

 if you didn't know any better， the fact that once you do it once you could do that same thing again and you could do it again you could do it 100 times。

 you can do it a thousand and so forth。😔，It's completely predictable。So， you know。

 what sort of tricks。Can we play within our system？

When we have a completely predictable access pattern。Yes， it's called prefetching。

 you've can prefetch ahead of the time that you're you know。

 well ahead of time you actually need to read thevalue， put it in the cache。

 it's just sitting there and so everything's in the cacheing。嗯，我要 asking你。Well。

 certainly you can decide what to keep in the cash。You know exactly the access pattern。

 then you don't have to rely on hereistic like LOU。

 you can actually just make an intelligent decision on what stays in the cache at any point in time that you need to evict something。

Okay。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_47.png)

Here's another one。Praer data placement across machines So what didn't mention is this parameter server。

It's implemented by giving random portions of the key space。

Now have the just space of the parameters。Spreading them across the different machines， in fact。

 usually the same machines as doing the work。So and that's called a parameter server shard。

 so parameter server shard for this particular machine is what are the which parameters am I going to actually store in that machine as part of the global parameter server so the global parameter server。

I's the collection of all these guys。All right， so given that I know the axis pattern。

 like this one does red， yellow， red， blue， and this one does green， red， green， blue。

Then I can do things like this， I can put the green over here on the same machine where a green at gets access a lot and red over here on the same machine where red gets access a lot。

Just to improve of accounting， right that's less stuff that needs to be sent across the network。Okay。

Any questions on that？

![](img/0f89cfa181fbefb97d0bb6160910e9cc_49.png)

All right， and there's a whole bunch more prefeing we just miss cash policies。嗯。

Numma wear memory placement。呃。And what yes。I felt parameter server is like a machine， only to stop。

Yeah， I should have mentioned that when I first introduced the concept， so parameter server。

Is when the programmer thinks of it as just this what's key value store， basically。

 I just I give a key and say I want to read， I get a value back。

 I give a key and an update and write and it causes that update to apply to the value associated with that key。

But if it really was just one machine， that would be a bottleneck。

 centralized bottleneck for their overall system， because I have。

 know a thousand worker machines and they're all trying to get their parameters served off this one parameter server machine。

So the way it's really implemented is that you run the functionality of that parameter server across a whole bunch of machines。

By taking pieces of the parameter space giving and assigning them uniquely to different machines。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_51.png)

。Like why do I have M broker？so。You wouldn't have to but。You know， if you。嗯。呃。

You could put them on different machines if you want。

 but we found that it actually is effective use the machine。

To have them have them both on there that somehow like the the ML worker is mostly。

You know it's not doing a ton of communication necessarily， you know。

 it's maybe getting hits in his cache and so forth and these parameter server。Sharards are doing。

 you know， sorry the。You know， they're hail a lot of the communication。And so， you know。

 it turns out to be a pretty good balance to have a worker machine and a parameter server machine。

on the same worker parametersmar over thread in the same machine。But you wouldn't have to。But yeah。

 this data placement。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_53.png)

Problem applies the most when they're on the same machine。

 otherwise you might place it on a nearby machine。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_55.png)

对。So when we do that， we actually get pretty nice speedups。嗯。嗯。What this is showing is that。

This is the time it took before we did all our optimizations， so we built the system it our store。

 it's a parameter server based system， it's running it's doing a collaborative filtering task。

Matrix factorization， recommending movies and things like that across eight machines。

And when we ran that， we did the training in this case took 152 seconds。

 but once we applied all the optimizations because we knew the access pattern。

 it went down to 36 seconds。Okay， and compared to GraLb on the same thing。

 GraLb was 507 seconds and then that's for the first four iterations， after 99 iterations。

 you know we still have a good lead here。So good way。Okay。

 so it ends up that this series of optimizations we're able to do because we know the access pattern speed things up by 45 x and makes things 11 times faster than GraphL。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_57.png)

给，你快写上来。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_59.png)

Okay。嗯。So what about the strgger problem？Okay。So I said that when you。

When you go to this bound scaleness。啊， model有有。It's a big win in terms of reducing the amount of synization communication。

And I said that if the horse race was tight。Then you would never have to stop。

But what if a horse race isn't tight， what if there's like consistently out of the？100。

000 horses in your race， there's still one that's behind。Okay。

 and so then you even if you're only waiting every S iterations， you know yes three iterations。

 you're still waiting。嗯。Okay， you still get sloweddown even with our techniques。

 so we came up with a different technique to address this issue。And。So we did the simple thing。

Which is， okay， if something's running behind， why don't we offload some of the work it's asked to do so that you know it will。

have less work to do and so it won't drag your wheel step。Okay。Now。

 typically way that's done is say Ido and Spark。Is that you just said， okay。

 when I see some worker that's going slow。Sdenly， I'm going to fire off another worker that's going to do that exact same task。

Okay， and then if that work also s fire， have a third worker and so forth。

 and so you're betting that the other future workers won't be one of these strrs。

The problem with that， and that's called cloning， the problem with that is that it breaks some of the mathematical assumptions of these machine learning algorithms。

😔，I mentioned there's a lot of flexibility in the way these works。

 there's a lot of tolerance for certain kinds of things。

But there's not tolerance for some other types of things。Okay。

And so the cloning technique doesn't work because of that。

 so we need something that ensures that you don't have two copies of something running at the same time。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_61.png)

哦，对。And what we're going to take advantage of is the following。

So in a general distributedtributive computation and general computation。It just competitions。

It's hard to know if you're behind your， are you distract driver？Okay。Because it's hard to。

Have a good grasp。How your progress compare to other workers。Because there's， you know， all sorts of。

Variations there's control flow and things like that。

 maybe there's you know there's a whole section of code you're not going to have to execute that another work is going to have to execute。

Unlike that general setting in this setting。You're iterating over the same input sequence every time。

And that progress。Dry that training data is a really good indicator of how fast you're proceed。So。

 what we do is。When you get to be 75% through your iteration space。Okay。

75% through your training data， sorry。For that durationation。You say， oh， okay， I'm 75% done。

 how does that compare to other？And you contact a few neighbors， a few of the other nodes， and say。

 I've hit my 75% mark， how are you doing？😔，Okay。And this so this guy is sending out the messages。

 this guy says I'm pretty close to 75%， so I'm okay， thumbs up， I'm doing well， okay。

 this guy is really dragging and he says， oh， I'm only at what is that like 40%。I've fallen behind。

And so let's take action now， let's not wait until all these other guys are done and notice this guy is running slowly。

Let's jump in， we know already that this guy's running slowly， so let's jump in now and fix this。

Okay。And we're able to do that based on these iterative progress measures， okay。

The second thing is that。the normal computation where you're running through a sequence of things to be done。

 there's a soup order that you've got to do these things。

You can't just pull out chunks of computation and hand to someone else。He to another worker。

Because I don't know maybe that works behind a computationalal branch。

 you may not even exit that at all， right？But in this world。

 training data is training data is training data。All right。It's effect fact。

This flow worker can do this training data in any order， it doesn't matter。Okay you just training it。

 You're just looking at and updating the parameters。 Okay， I mean， I it's got， you know。

 there's got to be some randomness in it and so forth， but。那。In general， it doesn't matter。

 so therefore I can identify and say， oh， you know what， just take the last， you know whatever。

 10% of my training data。And I'll give that to you， okay。

And he starts working on that and let's suppose that this guy actually finished that 10% and he goes back to the other guy and says。

 well， I'm done， how are you doing， says， well， I'm still behind。

 so let me give you I know 20% this time。Okay， and you go to the next 20% Okay so so this is completely out of order right。

 the original order was all this stuff then the green then the red。

 this is like this stuff to hear then some red then some green and then the rest of this stuff。

 but it doesn't matter。Okay。And so again， that allows us to be。Make this load balancing。

 this on the fly， load balancing very simple。Any questions on that？



![](img/0f89cfa181fbefb97d0bb6160910e9cc_63.png)

![](img/0f89cfa181fbefb97d0bb6160910e9cc_64.png)

And when you do that。You can see things like that the original was， again， this is time prorieration。

 so the original was much higher and the new thing we're proposing is about a factor to faster， okay？

Just by handling the strraggular issues in a better way okay and this is two different machine types on EC2。

 so this is second machine type shows the same result。

 these are on Azure instances the same thing we get about a factor of two。Okay。给一块时在呢。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_66.png)

Okay。嗯。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_68.png)

So the next one is parametermeter update importances。Okay。

So I've got all these things I want to communicate and all these updates。

 these parameters are' working to。And， you know， but I only have so much network bandwidth between these machines。

 it's the bottleneck。B God， you know， there's there's， you know， I want to。

Minimize the latency for things where they're stuck waiting on me and so forth。In general。

 computations， this should be computations。You don't really know how to prioritize the collection of markets。

collectionlection of messages between machines。In this world， you have interesting phenomena。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_70.png)

That。The magnitude of the peri is a really good signal of the importance， Imagine the other。

really good signal port up。Okay， so what that tells you is that if I'm a worker and I'm thinking about。

 you know， updates to send out。😔，I should start with the biggest ones。Okay。

 those are the most important ones to get delivered to fastests。All right。

 so early transmission of the larger parameter changes。

This is done up to sort of monitoring the bandwidth limit and making sure things are still within the staness limit。

And when you do that， you get， again， nice improvement。嗯。Of the green curve。

Whi is the does this technique in its system called Boin that we developed versus the red curve。

 which just does the banded staness number before， and this is the one that does fully asynchronous it's still I guess eventually converging。

 but it's taking its time。Okay， any questions on that？嗯。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_72.png)

Theicole this the data analysis neuro analysis slide from last lecture。

It's used for things like speech translation and object recognition images and videos and so forth。

 recognition face detection things like that。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_74.png)

嗯。O。So as before， each worker gets some collection of the training data and training data is in this case。

 say images and a label。Okay。I couldn't tell you what O was versus cipiter。

 but that's what you're trying to have the model learn。

We have our Emma workers and then we have one of these networks。

And these are the model parameter and the parameter server conceptually holds the networks。

The other thing that was， I believe touchedfts on last lecture is that。

The functions that are performed。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_76.png)

At each of these layers。Is sort of a dense matrix multiplication kind of thing and so it's extremely well suited for GPUs。

 And so typically these things are run on GPUs so。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_78.png)

So now we want a parameter server and we want to run it on GPUs。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_80.png)

And the way it works in training is that you have the images at the bottom and you do a forward pass where you compute the values going forward。

And the point to make here is that it's two layers of time， you use the outputs of the one layer。

As the inputs the next layer and then you compute the new values， okay。

 so you go to the top okay and then that's when you you so these are the different classifications the different types of birds。

And you compare and see where there are errors， and then based on those errors。

 you propagate back down updates to the weights on these edges， which are the parameters。

 the different weights on these edges。Okay。And then you repeat。

An important thing to note there is that it's pairs layers of time。

 you don't need to have all the parameters of the model in the GPU's memory at the same time。Okay。

 and so that's basically what we do is we use the GPU memory and we stage in and out pairs of these layers at a time。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_82.png)

And the rest of it hang out in the CPU memory which is typically considerably considerably larger than GPU memory。

 so there's space for the entire model there， we run our parameter server across the nodes as before。

 and when we do we actually get pretty nice results。嗯。

If you look at what the state of the art at the time， cafe， single GPU performance was。

 they didn't have a distributed implementation at the time。嗯。And what we're able to do。

 and this would be sort of if we could get linear speed up。 So across 16 machines。

 we got 16 fold improvement。 We don't quite get that， but we get。

13 fold improvement across the 16 issues。可以。那这块死了。Yeah。这啊其他地的。なか。So in the other。

 then do you worry about the training set that he's taking charge of getting my vote？チさん。

Because it would't apparently any more updates， yeah， that's also a problem。Definitely， but again。

 with our bounded staleness says they can only get up gas generations apart that you don't have to worry about that。

But that overfitting definitely comes into play。In a number of situations for the reason you mentioned。

 not just this one。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_84.png)

So that's an important consideration always。嗯。Okay。

 so the final one is that most parametermeter updates are insignificant。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_86.png)

Okay， where do you start so up until now and pretty much。哦。You know。

 machineachine learning distributed deep learning in the world is done。

 training is done in the context of a single data set。 a single data warehouse， single data center。

And so you're dealing with the properties of a controlled data center。But。You know， data， videos。

 images and stuff like that。Don't get generated at data centers， they get generated by smartphones。

And， surveillance and things like that。All over over the world。Okay。

 so the step that they're ignoring is how are you taking all this data generated all over the world and getting it into your data。

Okay。😊，It turns out that as we get more and more videos and more and more cameras and so forth。

 that gets ridiculously expensive and ridiculously slow， right？Moreover。Once we go internationally。

 we're just for personal privacy reasons。You can't move for our data。In many cases， right？EU。

 your European Union， has all sorts of rules about where raw data can be sent around。You know。

 images， medical images and so forth， right？And so it's often not permitted to even ship the data to the data center。

Okay。So instead， what you've got to do and we're sort of you know。😔，Again。

 leading the charge at getting people to think about this is you've got to do this training across the wide area。

 okay， not just within data center， you've got the data is going to stay where it is。Okay。

 all around the world。

![](img/0f89cfa181fbefb97d0bb6160910e9cc_88.png)

And you've got to do the training across the data，So and the problem there is that the wide Air network is ridiculously slow and doesn't have a lot of bandwidth compared to within the data center it's about。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_90.png)

呃。You know。15 x less bandwidth on average between these are the EC2 data centers around the world。

So even between these large data centers， there's about 15 x and up to 80x。Less bandwidth。

And the latency is higher and they charge you a lot， okay？



![](img/0f89cfa181fbefb97d0bb6160910e9cc_92.png)

So it's expensive。Okay， so the key idea that we have is that we're wanting to do something different across the data centers than we do within a data center。

And in particular， we're going to decouple the consistency model。

 the synchization model that we use within a data center from the one between data centers。

So within a data center， you've got the partition training datas before。

You've got your parameter server machines as before。

And we're going to run the types of models we've been talking about all lecture， okay？

But the difference is that。The model that we come up with。Is only going to be approximately correct。

 in a well defined way。That probably don't have time to get into。嗯。

Because there's all this other data centers and all this other data that's also updating these same parameters。

 and we're not seeing that data very often。Okay。嗯。And the key idea is that the while we run the usual。

Like I said， the usual stuff we were talking about a lecture within here， across here。

 we want to be a lot more parsimonious about what we said。

And we're going to use this feature I talked about before that says that the largest values。

 the largest updates are the most important thing to send。😔，Okay。And the key observation is that。啊。诶。

我我 going你 do为我 going to。Track how much the cumulative delta is for each parameter。

 so you do a little bit， okay， a little more， the more than one the more。

 and only when it gets up to be 1% change to the overall parameter do we bother a second。

And so and that's what we call anything less than 1%， we don't send it until it accumulates up to 1%。

 that's what we call eliminating insignificant updates， the ones that are less than 1%。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_94.png)

So the good news is it turns out that。So this would be not helpful if most of the parameter updates are large。

 but it turns out that 90 like 97% of the updates that these。

What shes want to do is less than a 1% change。Okay。So。

The reality is when we've been one these parameters servers。They're chatting all the time。

 but they're saying word。Most of the time they're like， oh， I've done a 。3% change I want to make。

 please， please make it。Okay， so if we just say， you know， talk to us when it's at least 1%。

Then we eliminate 95% of the communication。Okay so when we do that。

 we get results that look like this。Okay， that basically if this is normalized execution time。

 so the blue bars are and these are three different classes of machine learning problems。

The blue bars are just running it across the wide area， across the 11 EC2 data centers。Okay。

So that's the knife and do。And the O bars are what we're able to achieve， okay？So this is 3。

8 times faster， 3。7 times faster， on average classification we're six times faster。Okay。

And this is again， using our best models for each of the two cases， the GP and the CPU case。

And then we said well how close is that for the best you could possibly expect。

 well the best you could possibly expect would be if all the data was magically showed up in a data center ahead of time for free。

 okay before the experiment started， and so that's this case right here。Okay， the gray。

And so what we see is when we use our trick， we're actually able to almost appear as if we're running within the data center。

we're approaching the speeds as if we were running within a single data center。

 even though we're running across 11 data centers with terrible performance。

We're more than 40% of running on a single data center。And I mentioned this thing about cost。

 they charge you a lot of money to ship the data where you know， we save you， in fact。

 the cost to ship the data is more expensive than the computation， okay。

 this was a very expensive experiment to run。Mainly because of that。

 but we're able to save you factors between two and eight on the cost。

Because we're just shipping a lot less data。Any questions on that？



![](img/0f89cfa181fbefb97d0bb6160910e9cc_96.png)

Okay， good。嗯。The last thing I'm going to talk you about is。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_98.png)

This notion that does of the spotlight， that's kind of fun。Okay。

 so these data center provides back the con in data center。The data centers。Fends like that。E2。

 Amazon， EC2 say， okay， if you want guaranteed use of a resource， you pay vi。But you know。

 we've got some resources hey， the recurring either。You can benefit for those resources。

And we'll give them to you。As long as。Nobody that's going to pay more money wants for basically there's no guarantees that they won't be taken away from you at any point in time。

But they're 85 to 90% cheaper。OkaySo here's a curve of like pricing over a particular period of five days and this is the red and the blue are just two different types of machines。

 so this is saying here's the on demand price if you want to make sure your machine never went away you'd pay that price。

But if you wanted to play the spot market， then you could get it for these price。

And then you don't actually up paying this price way up here， you just get bumped。

Because you bid whatever price you bid， as soon as this jumps above your bid price， you get evicted。

Okay。And so there's definitely a possibility to get evicted。Whatever。Okay。

So what we did in this system called prous is well first we have a way to deal with。

Massive evictions of machines。In effect。But the other thing was we have a。あ笑说。

We learn a model of how to bid in our system to accomplish our goals。

So our goal is to get the capage done in a reasonable amount of time they were the cheapest price for。

Cars possible。And so what we do is we。It turns out that there's a co in the system。

I guess from economics survey，'d call it inefficiency of the market。

If you get evicted within the first hour of holding the resource， it's free。Okay。

I guess they feel bad that they evicted you so soon， okay？So our goal and our bidding strategy。

Is the bit a price on a resource that's going to get most of the way through the aisle and then the e。

So we want to be it。Because that's free computer。And we don't have， I don't show it here。

 but typically we can get about 30% of our compute absolutely free just by playing this trick。

And overall you can see that so this is our system here。

 we've reduced the cost from this dashed line。From here down to here。

And the runtime has actually also improved a little bit。

Just by using this aggressive bidding for cheap free resources and having a way of really dealing with large and we do diversification。

 you know standard stock market things right， we diversify in our case across machine types。

To try to make sure we don't lose our entire portfolio at once。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_100.png)

哎，你块的。All right so that's the story， there's a lot of things that are special about distinctive that are special。

 distinctive about big learning， that from a system computing systems perspective。

 you know notice I'm not changing machine learning algorithms， they're just running as they were。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_102.png)

We can use to speed things up。When you look at these slides。

 you can look at all the great students that have worked on this and so forth。

 and they also have the references in case you're interested in what the papers work in more detail。



![](img/0f89cfa181fbefb97d0bb6160910e9cc_104.png)

![](img/0f89cfa181fbefb97d0bb6160910e9cc_105.png)

And that's basically it。Thanks for great semester everyone。

 good luck on the final and wrapping up boxxy。And hope you guys。Where do I？

Ft like the course was good use of your time。And I guarantee you that this course。

 what you're learned in this course， will really help you in any computer science systems course you take。

From here on out， at C youR。Or you got your school whatever。来这。

