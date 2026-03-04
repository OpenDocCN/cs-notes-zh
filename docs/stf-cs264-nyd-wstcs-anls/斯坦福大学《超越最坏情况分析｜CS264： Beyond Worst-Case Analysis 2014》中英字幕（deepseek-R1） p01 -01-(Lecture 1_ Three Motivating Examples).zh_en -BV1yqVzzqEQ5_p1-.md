# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p01 -01-(Lecture 1_ Three Motivating Examples).zh_en -BV1yqVzzqEQ5_p1-

あ也是。All right， so welcome everyone， let's get started。So this is CS264。

 it's a sort of advanced algorithms or master's level algorithms class calledBeyond Wors Ca Analysis。

And every lecture I'll just you know at the beginning right on the board what's the plan for the lecture so today I'm going to start with a few motivating examples。

 you all hopefully know what worst case analysis is I'll remind you why we might want to do it。

 why we might not want to do it， and then I'll introduce the first kind of main concept of the course instance optimality。

Somewhere in the middle， I'll break and just talk about sort of course announcements and what's expected and so on。

 Okay， but I want to start with some motivating examples。

And so these three examples are meant to sort of clearly demonstrate the need for a course like this。

 the need for alternatives other than worst case analysis， so you know it's lecture number one。

 this is mostly for intro and motivation so the description is going to be kind of informal but these are all topics that we'll cover in more detail later on in the course。

Let me start by talking about caching。A problem that you've probably all seen。

 if not in an algorithms course， then in a systems course。So you have two types of memory， a cache。

 which is small and fast。And then a larger memory which is slow。这。

And depending on the context these could mean different things。

 you know maybe the cache is sort of an onship cache and the slow memory is main memory。

 or maybe actually the small fast memory is main memory and the large slow memory is disk， okay。

 those are just two examples。And so what happens is is you have a program requesting data okay And if the data is in the cache great。

 you just read it directly。 but if it's not， then you incur what's called the page fault or a cash miss and you have to pick a page in the cash for eviction and you have to bring in the requested page so that the program can actually read that data。

And so then of course， there's an algorithmic question。Which is when you got to evict something。

 what should you evict？And so let me just write this down and then I'll explain with an example。

So consider say a cache that let's say has room for four pages。

So pages are just sort of blocks of memory， if you like。And。

You're going along and some program is requesting various pages。So let's say the sequence。

The request sequence。So maybe the first four pages it requests for AB，C and D。

So you promptly bring those into the cash。Maybe then these is requested again， no problem。

 program has immediate access to it， maybe then A is requested， again。

 no problem sitting there in the cash available。Now the party is over once E is requested。

 so some fifth page， which isn't in the cache。So there's four things in the cache。

 We've got to kick out one of A through D to make room per E。Okay，It might get worse。 Maybe。

 you know， the next request is F。 And then again， we have to kick out one of the four to make room for F and so on。

 And it's not clear。 I mean， we have to make some decision。

 and it's not totally obvious how to do it。So。If， you know， as a thought experiment。

 if it turned out if we were actually cl vooyant and we knew everything that is going to happen in the future。

 then actually， this is a well understood problem。 Okay so when we get to E。

We have to evict one of ABC or D。 And what's annoying is whichever one we evict。Well。

 it might get requested again sometime in the future， so like if we evict A。

 maybe later A's requested to them we have to bring A back in， if A' is never requested again。

 then we have no regrets about evicting it now。Now， you know， if all else being equal intuitively。

 what do you want to evict， what you want to evict the page you're going to regret as late as possible so if A is going to be requested again tomorrow。

 you certainly don't want to evict it now because then you just got to bring it back tomorrow。

 but if A is not going to be evicted for like you know hundreds of thousands of more page requests。

 then it seems like a good idea to evict okay。So there's a heuristic known as furthest in the future。

 which says of all the pages currently in the cache。 figure out which one is going to be。

 like it says， requested furthest in the future and evict that。 It's intuitively a good idea。

 In fact， it's optimal。 It minimizes the number of cash misses over anything you could do。

 So this is a classic example of an optimal greedy algorithm。

But recall this was just a thought experiment， this assumed we had cl clairvoyance and knew when things were going to be requested next。

 mostly in the caching problem， you don't， you have to make decisions on the fly。

 so we need heuristics。So what kind of heuristics might we use？Well， let me get the ball rolling。

And' so just one thing you certainly could try， which is first in， first out。Or fiIO。

So this would just say everything currently in the cache。

 you see which one was brought in furthest in the past。Okay。

 and then if that's its sort of expiration date。 Okay， so far is fair。

 You've been here the longest you have to go。So which would we be evicting in this case once E shows up？

Yeah。So PhiO would evict a。Replace that with E。 And then when the F shows up， what do we evict？

So then when the F shows up， we evict。All right。So that's whatest sorry first in， first out would do。

And at the moment， it's not clear if that's good or bad，So what's another， you know。

 what have you heard of in some class that's perhaps a better heuristic than PIFO about hands？

Yeah recently used Yeah， so there's one called LRU。Or at least recently used。

 And so hear what you do。 I mean just like it sounds。 Okay so if everything in the past， sorry。

 everything in the cache， you look at when was the most recent time that it was requested。

 and then the one that was， you know， most recently requested furthest in the past。

 that's the one you kick out。So for LRU， when the E shows up， what are we going to evit？Bi。

So we're not going to evict a because a was requested very recently relative to when E shows up。

 so B is actually the most least recently used one。How about when the F shows up for LRU。

 we're going to evict？Yeah， C， right， because we have E A D all requested recently。 C， not so much。

All right， so you know at the moment I'm not going to， you know so you could ask which is better。

 so if you're implementing a cash in policy， which should you use？And， you know。

 I just want to point out the moment。 It's sort of not clear how to answer that question， right， So。

 for example， which of these， So these are two different caching policies。

 They did different things when E N F showed up， You know， and depending on what happens next。

 either way， you might regret what you did， right？ So if， in fact， after the F。A C shows up。Right。

 let's see。 So FiIO evicted， oh， sorry， the A and the B。 So if an A shows up next。

 you're gonna to be bummed out that you did PIO instead of LRU。 On the other hand。

 if a C shows up next， you're going be bummed， you did LRU instead of PIO or the reverse， excuse me。

 Okay so depending on which requests comes next， which of course。

 you don't know either one of these could look better in hindsight than the other。

 right because they made different decisions。O。So you could say， all right， well， you know。

 what happens in practice， What's true empirically and what you should have learned。

In a systems class like 140。Is it basically LRU kickicks but。 it's really good。In any case。

 it's certainly better than PFfo。Okay看。In fact， in practice。

 usually so LRU is sort of the gold standard and generally to implement LRU you actually have to keep track for all the pages in your cache when were they last requested。

 And that's actually kind of like a lot of work in some contexts。

 So what you often learn in systems is just how do you have good simulations of the gold standard of LRU using few resources。

 that's often what what you hear about。Okay， so。That's in some sense。

 we have this is the ground truth from practice that LRU is a good and excellent cashching policy。

And all right， So what's the narrative。 And so the reason why。 So I mean， so first of all。

 experiments show this。 But the intuition' is easy to glean。

 which is that in practical request sequences， practical data， if something was requested recently。

 it's likely to be requested again quite soon。 Okay， so it maybe be， for example。

 if they're blocks of a program。 you know， the program is working in some particular piece of code and you know doing some for loop。

 whatever it's using these pages。Another way to think about it is that the LRU assumption is sort of that the past is predicting the future and we know what to do if you're predicting the future you want to do furthest in the future so LRU is sort of a simulation of that benchmark。

 the furthest in the future algorithm if you assume that the future is going to look like the past。

 the recent future looks like the recent past okay so that's why the intuition， why it works。Now。

 believe it or not。And this is something I think you' all appreciate more in the next couple of weeks。

 It's surprisingly challenging to develop theory that conforms to， in some sense。

 this ground truth that we know from practice。 Okay， So a challenge for research。

Is to develop convincing theory that explains this well。系。

So the caching problems have been around forever。 So the furthest in the future algorithm that's due to belati That's from the 1960s。

 it's really only last decade that we started having truly convincing theory about how to think about the difference of why LRU is superior and that's some of the stuff we'll be covering in a couple of weeks。

 So one of the reasons you're looking ahead。 So one of the things we're going to have to do is're going to have to somehow model data。

 which is something you wouldn't have learned in an undergraduate algorithms class。

 because in some sense its properties of real data。

 which is what makes LRU better than PIFO So without modeling that aspect of the real world。

 you actually wouldn't expect theory to predict LRU to be superior so that's one of the things we're going have to introduce。

All right， so that's example number one。So example number two。

I'm going to draw from linear programming。And I'm not going to assume that you've studied linear programming。

 but I do hope you've heard of it。Okay。So what's going to be the issue with linear programming is again。

 there's going to be some so here not only is know the traditional theory not very convincing。

 it's just somehow outright wrong， so the kind of gold standard algorithm for linear programming。

 just the theoretical predictions for its performance are just way too pessimistic。All right。

 so what's linear programming， so let's start of the picture。

So the most interesting linear programming problems are in high dimensions。

 but just think about two dimensions for starters。 So you've got a feasible region。

Which in2D is a polygon。So these are all the things that are possible。

 and what you want to do is maximize a linear function with respect to this constraint set。

 Okay so maximizing a linear function is just like pushing as far in one direction as possible。Okay。

 so that's your objective。So the way I've drawn the picture。

 she a little awkwardly the way I drew the picture， but I think that's going to be the optimal point。

Okay， that's the furthest part in the feasible region in that direction。And so if you like。

More algebraberically。So this is you maximize a linear function。So C transpose x。

 So here x are the variables and C are the coefficients。 So C is telling you the direction。

So over an intersection。Of half spaces。Okay， so that's the polygon。In general。

 you would say subject to the linear constraints。A X at most B。 So here， A， B。

 C and X are all vectors and A as a matrix，So this is a very important class of problems。

 Those of you have taken C S 2，61， certainly know about it。

 very useful in practice to have fast algorithms for solving linear programming。

 it's sort of more general than lots of other famous problems like Maxflow matching and so on。

 yet it remains computationally tractable， both in both in theory and practice， in some sense。😊，Now。

 again。Just like with a caching problem， we somehow knew a good solution in the form of the LRU heuristic。

 here we know an extremely good algorithm。Which is called the simpleimpx method。Okay。

And I'm not going to explain right now what this is。 if you studied it great。 if you haven't。

 don't worry about it。 what you should know is just that this is super fast in practice。

 Okay so the empirical running time across， lots of different data sets。

 simplex method usually runs in like pretty close to linear time。

 where linear is the number of variables。 I。e。 the dimension of this space。 I。e。

 the length of the vector X。 that's the typical kind of performance that you see from the simple method。

 It's very old。 It's from the 1940s。 but kind of amazingly。

 despite the fact that there's been lots of developments in linear programming over the past know70 plus years。

 still typically today， you know most linear programs were solved using some suitably optimized variant of the simplex method。

 Okay， so it remains just a great algorithm for linear programming。😊。

So what does theory or specifically worst case analysis say about the simplex method？Well。

 so it' is a very cool but also very exasperating theorem。Of Cla and Minty。This is from around 1970。

Which says that if you look at the worst case running time。Overall。

 possible linear programs of a given dimension N。Of the simple X method。Then it's exponential。Okay。

 so rather than something like big O of n， it's something like2 to the n。Okay。

 so this is not some minor misprediction of performance。 I mean， this is way off。 I mean。

 this basically says simplex。 If you take this too literally。

 it says you shouldn't be able to solve problems with more than like 30 dimensions。 And really。

 simplex can handle problems with millions of dimensions。 Okay。

 so it's orders of magnitude off as far as the size of problems that you can solve。Okay。Now。

 to make matters worse， at least for the worst case analysis perspective， is on the other hand。

 there are algorithms which do run in polynomial time in the worst case。

 but empirically are far worse than the simplex method。

 The most egregious of these is method known as the ellipsoid method。

 that was actually the first ever proved worst case polynomial time linear programming algorithm。

 and it's actually theoretically very useful。 and it's a beautiful construction。

 But you never want to run， you never want to run it on real problems。

So we have sort of a double issue here， so first of all。

 it just says that at least for the specific context of the simplex method you cannot take worst case analysis very seriously。

 it gives you a disastrously pessimistic prediction of its empirical performance。

 but secondly if you take it too seriously， it actually just recommends the wrong way to solve the problem。

 you should be using the simplex method you certainly shouldn't be using the ellipsoid method to solve linear programs in practice。

So again， this disconnect。Motivates a challenge， which again， is is just not very easy， although。

 there's been great progress mostly 21st century。 and we'll talk about it。Which is developed theory。

 so an alternative to worst case analysis。To explain。Performance of the simplex method。

On real inputs。So I should say the example of Claan Minti is a sort of carefully contrived example meant to make simpleimpx perform poorly it's not like they took it from some industrial data set or something like that。

 It's a geometric construction explicitly concocted to prove this point。

And so what we're going to see here is we'll see won' here。 we won't do all the proofs。

 but I'll definitely tell you about sort of the theory。

 And so it turns out know you really can prove in a rigorous sense that the simplex method runs in polynomial time on essentially almost all inputs。

 Okay so it's sort of like an average case analysis， but on steroids。

 It's like a much more robust version of an average case guarantee。

 So that's something called smooth analysis and will spend three to four weeks on on smooth analysis。

 including its application linear programming deep in the course， Week 7，7 and 8。

 something like that。All right， does example two of why we need alternatives to worst case analysis。

Last example I want to talk about is clustering。 Okay。

 or some of you might know this as unsupervised learning。 Okay。

 so finding patterns in unlabeled data，So you know you want to think about something like maybe you have a bunch of images and you somehow represent the images in Euclidean space。

 maybe by their bitnas or you have some features for them and you know you're hoping to just sort of identify meaningful groups。

 maybe these are pictures of cats， those are pictures of dogs， something like that okay。

So goal detect meaningful groups。And so usually the real problem in clustering has this sort of modeling issue that you know you sort of know a good solution when you see one。

Right sort like， if you show me the cluster like， oh， yeah， it's a cluster。 Show me a different。

 you're like， now， that's a bad cluster。 right， But you know， to really have an algorithm for it。

 you you need to have some more precise approach。 And so the way usually people do this。

I they take an optimization sort of approach， So they specify some kind of numerical objective function defined on clusterings。

 Maybe you've heard of things like k means or k median， these are examples， but as many examples。

 and then having posited this objective function on clusterings。

 you just optimize okay you find the clustering which makes this objective function as high or as low as possible。

 depending on if it's a minimization or a maximization okay。So positive objective。And optimize it。

Okay。And we'll talk about some concrete formulations a little bit later。But the。

 the main points really cut across， you know， all the ways that people formulate clustering problems。

 So what is theory say， theory says that。These are NP hard problems。

So for all of the standard objective functions， K means K media and etc cetera， it's N hard。

 define the best cluster。 And of course， MP hardness， as you know。

 that's that means in the worst case。 It's a worst case notion and B hardness。

So what's true in practice？Well， in practice。You know， the clustering problem。

 maybe it's an exaggeration to say it's viewed as well solved， but I mean。

 people successfully solve clustering problems to a degree that they're happy with a solution all the time。

Okay， so let's say fast algorithms。Usually give。Meaningful results。Okay。

 so maybe they get a few points wrong， whatever， but you know。

 you basically get your cats and dogs back in lots of different data sets。All right。So once again。

 we have a disconnect。So the clustering problem， once you formulate it as an optimization problem。

 and you apply the worst case lens， you get MP hard problems。

 yet somehow lots of algorithms are doing something interesting and we want to understand why。

So the challenge here for theory。Is to formalize the following idea。So the thesis is that。

Cluing problems。Its hard。Only when it doesn't matter。So what do I mean， Well。

 when do we care about clustering， We care about clustering when there is a meaningful clustering to be found。

Okay，Now you write down an objective function， like an optimization problem。

 And it's well defined whether or not there's a meaningful clustering。 Okay。

 And to have a worst case algorithm， it means you have to solve every single instance。

 whether there's a meaningful solution or not。Okay。And somehow， the belief。

 and we'll look at recent attempts to formalize this is that， well。

 if there actually is a meaningful cluster there， then somehow that should the input should have extra clues。

 Foholds for an algorithm to make use of。 And so somehow these cases of the problem should be easier than the worst case。

 So we might hope the clustering algorithms could do better in the worst case on the instances that we actually care about。

So that's been a pretty hot topic for the past five years or so。

 and I'll definitely survey some of the key results。About midway through the course。All right。

So those are the examples。Now that we have a quorum， let me just say a little bit about the class。

 So what， so what are you want， You're probably wondering， what do I got to do。All right。

 so here here's what you have to do。 So there's going to be weekly problem sets。

 They'll go out Wednesdays。 startinging this Wednesday。 They'll be due a week later。

They'll be composed of both exercises and problems。

 exercises are just sort of lecture details to be filled in， they're not meant to be very difficult。

 they're just sort of a framework to keep you keeping up with the lectures also it allows me to kind of defer some of the less interesting points from the lecture and focus on the good stuff。

 the juicy stuff and lecture， and then you can fill in some details on your own。

Then therell also be some problems。 There'll be harder， but there'll be few of them。

 And that's meant to further development in lecture。 So often I'll discuss， you know。

 an idea like today， we'll talk about instance optimality at the end of the lecture。

 And I'm only going to have time to give you really one juicy example about instance optimality。

 That'll be on Wednesday's lecture。 But through these problems。

 you'll see that it also can be applied to other problems as well。

 And that's really one of the things I want you to take away from the course。

 know here are other ways you can think about designing and analyzing algorithms。

 But you know I also want to give you enough examples that you can imagine how you might then apply them to computational problems that come up in your own work。

 so in the lecture， I'll give you some examples but the problems will develop more。Okay。

 so some some okay， so some second order points around the homework。

 so if any of you are more interested in kind of delving into the research literature。

 there's an option that's totally optional， but if you prefer you can skip some of the problem sets。

 namely the last three out of the nine and instead read a paper or two and write a say ballpark 10 to 12 page paper summarizing what you've learned okay synthesizing one or two research papers。

So that's an option， but again you don't have to do it。Secondly。

 I always require less of the past fail students from the letter grade students so if you you know you can also audit。

 of course， but you know for a lot of people， a sweet spot is sort of you take a pass fail and then it's sort of a forcing mechanism。

 you actually come to class， you know the whole quarter and so on。

 and so then you know be explicit on the problem set instructions。

 but roughly you have to do kind of half the work of the problem sets for a pass fail grade okay。

All right， other announcements。And the green is Richhi Gupta。He's your trustee T A。

 He took this class a few years ago。 and he works in this area。

 so he knows lots of stuff about everything I'll be talking about。

Office hours will be posted later this week。What else， Oh yeah。

 So there's no textbook Basically this class doesn't exist except for you right here at Stanford。

 the one you're taking pretty much there will be videos as you can see。

 those should be up on the website within one to two days after the lecture I'll also be doing lecture notes。

 that'll take a little bit longer， but hopefully you know unless I'm traveling or have a huge deadline say within two to five days after the lecture。

 so I'll do my best， but I can't absolutely promise you'll have the lecture notes before homework is due it's sort of best effort service if you like。

Okay， so questions about the course or about the motivating examples。Anything on your mind Yeah。

 you have a question the objective Yeah I mean nonlinear because like you said before theres the method which solves generally。

 So so for linear programming， you need linearity in two senses。 So the question was。

 you why can't you combine。 why can't you apply example number two to example number three。

 That was basically the question。 So linear programming， you need linearity in two senses。

 So first of all， needs to be the objective function， which actually is the case for many。

 but not all of the clustering objectives。 So you also need the feasible region to be convex。

 The intersection of half spaces。 And so clusterings are discrete objects。

 So the feasible region here is more of an integral discrete flavor。

 And if you have linear objectives and you have a discrete solution， those are often NPhar。

 And that's the case for clustering all of these clustering problems。Other questions。Okay。Yeah。

We will， we'll have one to two lectures on semi random instances。

There's been a lot of recent progress on that topic， but it's very technical。

 So I'm trying to see if there's some simple nuggets I can disill out。

 but there'll be one lecture for sure， yeah。For graphs or for other things。

 or what were you wondering about？Other questions。Yep terms no。We're all adults here。No midterms。

 no finals。Other questions？All right。Okay。All right， so having covered these examples。

 let me zoom out a little bit， okay。And let's just be clear about something。

 let's try to be clear about， you know， why are we even doing this。

 why are we bothering to try to analyze algorithms mathematically as opposed to just like， you know。

 randomly thinking of some and then running them and see how they do on some random instances that we sort of dream up。

So what is the point？Of the mathematical analysis of algorithms。

And one thing actually that even sort of seasoned researchers sometimes lose sight of is there's several conceptually distinct answers to this question。

 I'm going to give you three and different types of research in algorithms are really geared toward different ones of these answers。

 that's worth keeping in mind。 They're all good answers。

 I I just want to realize that they're different。All right。The first thing， the first potential goal。

I should say all of these are pretty challenging to achieve。

so we've been doing the mathematical analysis of algorithms for over a half century。

 and I hope you learn a lot in this class， but you'll also probably come away with the feeling that it's amazing we don't know more。

 and so there's lots of research to be done here too。So first goal。

 why do mathematical analysis of algorithms， Well， especially if you have some algorithm in mind already。

 Okay， so you already think you sort of know what you either you have to use a particular algorithm or you have a gut sense that it's the right algorithm。

 You might want theory to give you an accurate prediction of that algorithm's performance。

 How well it's going to do， okay。So predict。Empirical performance。 Let's say， predict or explain。

So maybe you even already know the performance and you just want a good mathematical model of why it performs the way it does。

So predict or， explain empirical performance。And you know。

 exhibit A here is probably the second motivating example I gave you， which was linear programming。

 Okay， so simplex algorithm， it's not so much， you know。

 when we're trying to analyze the simplest algorithm。

 it's not that we're looking for some new linear programming algorithm。 We're in some sense。

 totally happy with the one that we have because it's awesome。

 But we's's just not acceptable to lack a theory that explains why it performs so well。

 So here it's almost like we're playing the role of a scientist。

 we observe this natural phenomenon that this algorithm is super fast。 we want to understand why。

 what's the right way to explain or think about or generalize why it has such good performance。😊，Now。

 one of the reasons why this is hard and this is something you don't see as much in undergraduate algorithms is a lot of algorithms just have wildly different performance on different inputs。

 And again， simplex is a good example linear time， lots of the time。

 but there are these weird inputs where it's exponential time and they're really there。 I mean。

 they're not they're real examples where it really does take exponential time。

 So it's not even really clear what I mean by talking about the V performance as a singular of an algorithm because it can vary。

 it can vary widely So how do you reason about that it's not easy。Okay， that's the first goal。

Just predict to have a good prediction of how well an algorithm is going to perform or a good explanation。

If you already know how it performs。So goal number two。

 and this is probably sort of maybe closest to at least the way I teach undergraduate algorithms。

Is we're really looking for advice right So we're kind of thinking of ourselves as like you know the end user right So many of you will be to go on to be software engineers。

 you'll be in this perspective。 You kind of figured out what kind of problem you have。 know。

 you figured out it's the shortest path problem or whatever。 And you want to know look。

 I know there's several algorithms for shortest path。 I can dream up some more。

 which one should I use Okay Tell me what to do。 tell me the best algorithm All right。So， rank。

Different algorithms。By performance。All right。Now， I want to point out， so you know。

 while goal number one and goal number two， you know they're both sort of pointing in the same direction。

 they're both asking for kind of a good understanding of algorithm performance。

 they really are incomparable。 you can really solve either one without solving the other。

 So specifically you could have a mathematical analysis like worst case analysis。

 which maybe it's very pessimistic So if you're using worst case analysis。

 maybe it always overestimates the performance or sorry it sort overestimates the running time。

 let's say of every algorithm， But if it still gets the ordinal ranking correct。

 you still just read off the best of the algorithms。

 It actually is excellent advice about which one to use Okay so you can solve and there are plenty of examples and we'll see some where you can solve the second goal without solving the first you shouldn't take sort the predictions literally。

 just their ordinal ranking。Conversely。When you do when you do explanation or predictive work。

 usually you have a fixed algorithm in mind。 So for one algorithm。

 you might have a very good understanding of if it's fast or slow， but you know。

 there's other algorithms out there which your analysis doesn't apply to。

 So usually when you this may seem stronger。 but generally， you know。

 the theorems you prove on goal number one don't allow you to just immediately solve goal number 2。

And again， the reason I'm teasing these apart。 I mean， later on。

 you're going to learn a lot of different ways to model algorithm analysis。

 And so we'll keep revisiting these， you know， to clarify which of these goals are we trying to achieve。

 And then， of course， once I tell you about what people have done。

 we can assess have they achieved it or not or to what extent。So we'll come back to these。

 Don't worry， But I just want to kind of lay out the land in this first lecture。All right。

 so here's goal number three。Which is the one researchers are kind of， you know。Most familiar with。

Researchers and algorithms， at least， which is to guide the development of new algorithms that we haven't yet thought of。

Okay。So whenever you have some sort of performance measure， like， say。

 the worstcase running time of an algorithm， it gives you。

 it sort of gives this yardstick that then focuses the effort of often lots of people to devising better and then hence new algorithms。

 And if you think about it， a lot know again， when I teach undergraduate algorithms。

 often I'll teach know I'll teach you the end squared sorting algorithm。

 And then we can we do better So we just have this like yardstick and want to keep getting lower and lower and lower and lower。

 and to take a step lower。 We have to have a new idea right And those are sort of know treasures and algorithms research。

 new ideas for designing algorithms。 So the reason people sort of want to do this mathematical analysis。

 have these yardsts is to really guide you to new ways of solving problems。😊，All right。And right。

 So I should say， you know， it， you know， for this to be justified。

 it is not crucial that the new algorithms that you develop are automatically say practically useful。

 Hopefully sometimes they are。 But， you know， just sort of having this kind of analysis framework。

 if it， if it sort of organizes your brainstorming。

 that's actually a very productive application for the theory。All right。So。Let's。

Just be clear about what I mean by worst case analysis。As you've seen in undergraduate algorithms。

 and let's review from undergraduate algorithms why this can be very useful。

 And then let me just sort of reiterate why sometimes it's inadequate。

 which is the point of this class。So by definition， what do I mean by this？So you have an algorithm。

 and it performs differently on different inputs。 Worst case analysis just means you only pay attention to its worst performance on any input。

 Okay， so you summarize the performance。Of an algorithm， very coarsely。So even an algorithm A。

So I'm just going to write cost。Of a comma Z。For let's think of it just being the running time。

 if you like， of a given algorithm A on a given input Z。

Worst case analysis just says you look at the max。Overall， input Z。 often。

 this is parameterized by the input size， right， So you think an hour than having worse case running time O of N log n。

 Okay， something like that。I want to emphasize that the comments I'm making and the examples we'll see in class are not limited to just running time。

 this could be there's lots of other cost measures you might care about， you might care about space。

 you might care about input output operations， we'll see a lot of examples where what you care about is solution quality So you're trying to find a good traveling salesman。

 something like that and this would be the solution quality of the output of a heuristic。

So that's what I mean by worst case analysis。Any questions about that？So， for example。

 when I teach undergraduate algorithms， I think at least 90% of what I do is in this。 Okay。

 so this is really sort of the dominant paradigm for algorithm analysis。Okay， so why？

What's the excuse？It's a reason。Well， so the first reason is in the happy case where you can prove a worst case bound。

 which is good。Then you know， you're home free。 basically， you can just， you know。

 forget about the problem。 You just have a， always awesome solution to the problem。

So good upper bound。嗯。Basically， awesome algorithm。And you know in undergraduate algorithms。

 I sort of cherry pick examples where this is the case。

 So the bulk of the algorithms that I teach have worstcase running time close to linear And there are problems where you have to read the input。

 So no algorithm is going be better than linear。 so their algorithms which basically you know。

 the algorithms it almost reduces to reading the input and that's just sort of the holy gra algorithms。

 That's just something you can put in your pocket。 whenever your data fits in May memory。

 you can just take it out of your pocket and apply it。

 maybe you don't even know why You don't even know why you want to sort。

 You don't even know why you want to do a shortest path。 know this kind of thing。

 but just do it for fun。 it's harmless right。I call them four free primitives， okay？

So that's one thing is in the happy case where good good upper bounds exist， you're just very happy。

 There's no， no one can argue with you，Another reason。Is that it's often easier to analyze。

RightSo it's pretty amazing。 It's pretty great that in an undergraduate class， you know。

 which is probably half sophomores， I teach a complete analysis of， say。

 the running time of quicks sort or the running time of Dykes's algorithm with heaps。 I mean。

 it's completely fundamental。 These are cornerstones of computer science。

 And yet I can teach these proofs in a fraction of a lecture to sophomores。 It's amazing。 It's great。

😊，And it gives you great advice about how to solve those problems。

And the other thing I want to point out is， you know。

 so you could criticize worst case analysis as being unrealistic， and it is。But， you know。

 one thing to keep in mind is， you know， realism per se is not， you know。

 usefulness of a model is not necessarily monotone and it's realism。 All。

 So a more realistic model from which you cannot deduce any conclusions because it's too complicated and detractable is not helpful。

 Okay， So we're really we're always looking for the sweet spot and modeling of retaining enough of the salient properties of analysis。

 subject to just being able to deduce conclusions for them。 So maybe this is too far on one end。

 you know， maybe this is too simple。 But remember， you know， more realism isn't always a panacea。

All right， so three。The third pro， which is sort of related to number one。

Is that you don't even need to try to understand your inputs， okay。

You do not need any kind of domain knowledge to feel confident that running this algorithm is a good idea。

 Okay， it's just an input by input guaranteed。 It's always good。Okay。

And there are contexts where that's exactly what you want， right。

 So think canonically say about sorting and searching， right。

 So imagine you you've been tasked with writing the default sorting subroutine for some new programming language。

 Okay which you're hoping is going to go viral and be adopted by millions of people Like what's your domain knowledge about these millions of different people that are going be invoking your sorting routine。

 you have like none， basically， you have no idea。 Okay。

 you really want it to be useful spanning lots of different application domains。 Okay。

 so in that sense， this really is the kind of guarantee that you want。All right。So lots of reasons。

 lots of reasons to use it。So the motivating examples have sort of already exposed to the reasons why you might not want to use it。

 But let me just kind of summarize those succinctly here。So the first one is sort of obvious。I mean。

 evidently， I mean， this is really the most pessimistic summary of an algorithm's performance that you could ever use。

 You cannot be more pessimistic than this， right。Which is fine。 But I mean， the worry is that。

 at least especially if you think about that first school about predicting performance。

 then this probably seems a little crazy， right， I mean， this is potential to be wildly inaccurate。

 a summary of how how how well algorithm going to perform empirically。 Again。

 simplex being sort of a canonical example where you just have a radical mischaracterization of simplex's empirical performance by focusing on that worst case。

😊，So pessimistic， but the point really being therefore inaccuracy， okay potentially。

And sort of for this reason， because you can be， once you're sort of very inaccurate。

 then it opens the possibility， you'll start ranking algorithms very sort empirically incorrectly with respect to each other。

So can rank algorithms。Incorrectly。So for example， in the caching problem。

 it doesn't actually say the theory as we'll see in next week。

 it doesn't say that F5IO is better than LRU， it just says they're basically the same。

 it says it doesn't matter so that's not very helpful linear of programming as we saw you really just you know the advice is just very bad。

 poor that comes out of worst case analysis it's a simplex is bad and other things are good。O。

So the third con that I'm going to list is actually the same as the third pro。Okay。So in some sense。

 the strength of the worst case model。Is also its weakness。So a couple of things， so first of all。

 you especially if you're designing an algorithm that's at least sort of for some domain， you I mean。

 generally practitioners like to think of you there's some model of data。

 you know maybe they can't articulate it， maybe they don't know what it is。

 you know maybe they believe in some generative model and maybe they don't。

 but there's still some notion of like the data sets typical to this domain or typical to the real world。

And if you think about it， the worst case model， I mean， in a strong sense。

There is no coherent model of data， model of the world that corresponds to the worst case analysis perspective。

 or if there was one， you have to call it the Murphy's law data model right because like literally。

 like what the input is depends on the algorithm that you choose。 You choose the algorithm A。

 You're gonna get the worst case for that。 use algorithm B you're gonna to get the worst case for that。

 right So it's just in coherent。 So it doesn't make sense。Furthermore。

If you think about the first motivating example in the third one。So caching and clustering， you know。

 the properties of actual data is crucial to deducing what we sort of know to be true， right。

 so in the cacheching context， we know that LRU is better than iPhone phone。

 and we even know the reason is because real data has locality of reference， okay。

And you know and you could， you know， And so really。

 you need to be able to articulate that in your model。

 if you expect to be able to drive the conclusion that LRU is better than PIO。

 Similarlyly in clustering， it's not that we really are sort of objecting to theory saying that these clustering problems are hard in the worst case。

 We're not really refuting that。 Again， we're just saying， well。

 properties of real- world data mean we're not in these hard instances。

 Okay And the key thing is if you're doing worst case analysis that know by construction。

 there's no way to articulate any kind of special properties of your domain。

 Okay it just takes that language away from you。 Okay， you're just stuck with the worst one。

So understanding lots of algorithms， understanding lots of problems。

 you need some sort of part of your model that allows you to encode domain restrictions。

 worst case analysis doesn't give you that。Okay。2。So those are the pros and cons。

 any questions about any that？Then。Oh right。 So why did I do this， Right， So I want。

 let's judge or let me， let me sort of opine how well worst case analysis does with respect to the three goals。

 Okay， I just erase the first two。 Here's the third one。

 So why do a math why analyze algorithms mathematically。Empirical predictions of performance。

Ordinal ranking of algorithms so that， you， you know which one to use。

 which one's going to do the best and guide the development of new algorithms。

So I would say that on this third goal， worst case analysis has been just， you know， runaway success。

 Okay， really， it's LED to the development of a huge number of new algorithms。

 new ideas for tons of different problems， tons of different data structures。

 some of which have been useful。 So that's been great。 Okay so I'm really not here to criticize it。

 Okay I'm here to really complement it with additional modeling tools。😊，Now， on the second goal。

 this was the ordinal ranking。Here， it sort of depends on the problem。

 I mean I I could tell you lots of problems or rather you saw lots of problems in undergraduate algorithms where it gives you actually really good advice about how to solve problems。

 Hey like Dykes's algorithm implemented with heaps it really is a great way to solve the problem。

 It's good in both theory and practice。 I could also give you lots of problems where it gives you bad advice。

 In fact， you saw sun in this lecture。 so it's sort of medium on sort of ranking algorithms。😊。

On the first goal， predicting performance， I would argue it's clearly just not meant to do that。

 Okay， it just really is pessimistic for， you know， again， if your worst case almost linear time。

 there's only so pessimistic could be because you have to read the input。

 There's only so far off it could be。 But， you know， modo， that exception。

 you've really kind of as soon as you adopt this given up on， on making serious predictions。

 that's really not what it's meant for。Okay。So， that's my summary about。How the report card。

 if you will， for the dominant paradigm on these research goals of giving。

So I want to introduce one new concept before。I leave you today。Just is that of instance optimality。

Okay。Oh yeah。 So this is。As a concept， this was really emphasized by Faagagin， Loum and Noir。

So on the web page， I'll be putting links to references if you're curious if you want to delve deeper。

And one thing that's cool is this paper actually just this year in 2014 it won one of the big Test of Time awards。

 it's called the ACM Girdel Prize， which is given once a year to a sort of influential theory paper from the past 12 years or so。

 so this instance Auto paper just won that this year。All right。Within this optimality。

 it's very clear which of those three goals that we're focusing on。 Okay。

 we're really focusing on goal number  two。 So goal number two is one which says， you know。

 I don't care about predicting performance per se。 Just tell me which one's the best， okay。So。支uch。

Rather than tell me which one's the best， Let's start with an even sort of simpler problem。

 which is suppose we just have two algorithms on the table。 A And B。

 Just tell me which one is better， okay。So how would you answer that question？ And again。

 what I want to emphasize is， you know， remember already in the caching problem。

 we saw the issue with LRU and PIO， which is， you know。

 I can show you sequences where PIO is better than LRU。It's not hard to construct them。 Of course。

 I can show you sequences where an LU is better than PIO。

 So they're sort of incomparable unless you willing to sort of sit down and make， you know。

 answer hard questions about how to trade off different inputs，So this week。

 what I'm going to do is I'm going to basically show you some very happy cases where we can punt on trade offs between inputs and just say something very strong。

 there aren't a lot of problems that we can do this for but there's a couple and I'm to want to start the course with those。

So suppose you wanted into a really uncontroversial way to say an algorithm A was better than algorithm B。

Gs。So in which situation could we do this without， you know。offffending anybody。Without。

Inviting any debate。Well， we'd have a very clear answer if one of the algorithms dominated the other one。

In the following sense。Suppose that A was just better than B on every single input。You know。

 as long as you believe in the cost measure， okay， which we're just going to take is given in this course。

 again， the cost can be running time， space， solution quality， whatever。

 So if we've agreed on the cost measure， And if this is true。

 no one in their right mind could suggest using B over A。

 They'd have to agree A is the better of the two algorithm。Okay。Alright。

 so that's the simpler question。 how do you answer a question between two algorithms。

 So now let's return to the question。 how， you know。

 So if you wanted to say that an algorithm was optimal in an uncontroversial sense。

 what would be a proposed definition。And that's the notion of instance optimality。Okay。

 so algorithm A。Is instance optimal。If star holds， So if a dominates every other algorithm，Okay。

So if you， if you have a problem and you can find an algorithm。

 which is instance optimal in this sense， this is， you know， the definition of a no brainer。 Okay。

 always use algorithmic。 And again， remember， the goal here， the goal is， you know。

 is there any case where we can not even worry about what the input is， Okay。

 there's no hard compromises to make across different inputs。 And this is it， okay。So for example。

 we know that you know if we take A and B to be LRU and PIFO and we take cost to be the number of cash misses。

 we know that this inequality does not hold in either direction for LRU and PIFO so this already is getting kind of rare that you have two algorithms or one is always better than the other to have one algorithm which is always better than everybody this is a very special case indeed。

 actually to be honest with this definition exactly as stated。

 I don't know of a non-trivial problem for which there exists and this optimal algorithm so remember always remember。

 you know definitions are cheap until you see examples right。So for here。

 I don't actually know ancient examples， but if we relax it in two reasonably modest ways。

 there are examples。 and that's the point of this week。So relaxations。

So the first relaxation is that we will allow a small， constant factor， maybe something like two。

On the right hand side。So while maybe a isn't strictly better than every other algorithm B on every single input Z。

 it's， you know， never outperformed by more than a factor of two。 Okay， so in some sense。

 you regret for using a instead of some algorithm tailored for the specific input is bounded and small。

 Okay， so that's the first thing。The second thing。Is that？We will restrict。Bi。2。

But I'm just going to call informally natural algorithms。Okay。

So notice in the definition of instance optimal， the way it's written。

 it says that a should dominate every single algorithm B， no matter how crazy it is。

 So the relaxed version is going to say a should dominate every natural algorithm B。Now。

 the definition of natural sort of depends on the problem。 But intuitively， what it's meant to do。

 it's meant to prevent。 it's meant to disallow algorithms， which in some sense。

 have memorized the solution to Z。 Okay， and those are the kind of algorithms that sort of。

 for uninteresting reasons， make this guarantee impossible to achieve。 And again。

 we'll see both in the examples that you study on the homeworks and the ones that I'll talk about at length on Wednesday。

 There's a very natural， you know， and。You know， pretty uncontroversial way to define natural algorithms to prevent that memorization。

So in the homework that I'll go out Wednesday， I'm going to ask you to study the model originally proposed by Fagin atal。

 where they first explored this notion， that's motivated by the problem of searching a bunch of sorted lists。

 and so you have a mixture of sequential and random access and you pay for every sequential access and they propose an algorithm which is instance optimal in this sense。

And again there's some natural notion of natural algorithms and also they have a small constant factor here and then on Wednesday I'm going to show you that really for a fundamental computational geometry problem that of identifying maxima of point sets iss a very old algorithm from the 80s and it's a beautiful divide and conquer algorithm and that turns out to be instance optimal again among in some sense all algorithms that can't memorize the input so that's what's coming up I'll see then。

