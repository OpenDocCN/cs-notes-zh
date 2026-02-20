# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p17 Lecture_17_Experts_cont_.zh_en -BV1a4cCeMEzb_p17-

Let's get started， we have business to transact。😊，We want to study the experts problem again。

 remember the experts problem was at each point in time you get prediction you have a bunch of experts and experts。

You get a prediction。呃。From each expert and you want to make a prediction yourself。

And then you make a prediction， you see the actual outcome， you get a mistake or not。

And you want to minimize the total number of mistakes。

And we saw a deterministic algorithm multiplicative weights。

 which did about twice as well as the best export。😊。

And then we said oh deterministic algorithm not so good。

 so we should look at randomized algorithms and really randomized algorithms were pretty much the same as looking at if you're looking at expected loss。

 this is the same as looking at these dot products so we abstracted it all out into the following fairly clean game I really like the way this looks at every point in time you play a vector。

 the world play the vector the dot product is your loss and that's the that's the long short of it。😊。

you play a vector， your vector must be in the probability simplex。

 so this is like giving you a distribution over experts。😊，The word play the vector。

 which is giving you a loss between0 and 1 for each expert and this you should view really as the expected loss。

😊，But geoally， it's very simple vector vector dot product， that's your loss。

You want to minimize this in the long term。So this happens day in day out。

And what I'm claiming is that this algorithm， which we willll go over in a moment。

 ensures that the dot product came。The total loss you suffer is no more than one plus epsilon times the loss of the best expert。

On this particular sequence。Plus。Garvishdom， this is。

This is some so loss that you will suffer regardless。Okay。😊。

So really this is like the best expert plus a little bit of loss。

 so plus loss how much epsilon times the best expert loss。😊，Plus， login over Epsillog。

So these two terms together are known as the regret of the algorithm。

And very often well talk about low regret or you know people call it vanishing regret， low regret。

 sometimes we say no regret algorithms， but no regret is only in the limit。😊。

So this is exactly the correct term and here's here's one。😊，Immediate implication of this。

That the regret。A that most epsilon times t， so this is epsilon times。You know， in key time steps。

The best expert can suffer no more regret than capital。Plus。Log and over epsilon。

 this is just a second term。Yeah。And this， so if you set。

Epsilon to be something like square root log n over T。Then this ensures。Then those exact。I that most。

How much。Tod square root。嗯。😊，好。So the total loss over the best export is this quantity。😊。

And this is growing linear sublinely， this is going you know like square root of t over t rounds。😊。

So this this term is getting vanishingly small compared to。He。

And this is kind of the main idea and in fact， you could just say regret divided by T。

This is the average regret。Is this divided by t， which is like two square root？狼嘅。我不哒。

I'm not saying anything new， this is just a little bit of calculation。😊，But the regret is sublimar。

And this is this is often we say， well， the algorithm must be learning。😊，Because， you know。

 if you say， oh， the regret is linear for a problem， the algorithm cannot learn。So这是 some的二个这么句种。😊。

Yeah。But I'm not taking a learning perspective， I'm just taking this as an algorithmic problem。😊。

And we'll see how to use this to actually solve zero sum games， which are a special class of LPs。

 actually there's no no more special but than any other LP， but you know at least it's easy to state。

😊，And then we will talk about how to use this resolve piece。

So this algorithm will actually solve linear programs for you， not the best running time， but hey。

 John。😊，我你语我着出先。So。What does it mean？It。The experts pro the loss of the best expert if you're absolutely good so this is just saying。

EI is just the I basis vector。😊，So this is just the loss the best of the IT expert。😊。

Summed over at all time。And the men is just saying this is the best law。

 so this is again the best export。Good。And another way of saying this often people say is for all eyes。

😊，Dis guaranteear。Basically， you can back any eye you said， you know。

So one way I always think about this， I might as well again share with you again pictures and phrases that in my mind I might as well tell you。

 nobody should be able to come tomorrow and say， you know， I listen to expert7。😊。

And I'm doing so much better。That won't happen。Okay。So， by the way。Yeah， good。

Let me let me talk more about this Oh okay and I should tell you the algorithm as well。

 the algorithm is pretty much what we talked about last time I want to maintain weights on every export。

😊，And the weight start off at uniform。You can change this and in fact。

 if you already have priors on the experts you know this expert is much better than that expert。

 you could put more weight on a better expert。😊，And you can give more nuanced guarantees you know。

 it'll come out later when we talk about continuous optimization you'll see better guarantees right there you know it'll just pop out okay the probabilities will always be the normalized weights。

😊，So， this is the weight of the IF expert divided by the total weight of the all the expertss and at time T you penalize the IF expert according to how much loss itself。

😊，And this morally again， this is this is approximately WTI times1 minus epsilon。😊，はい。

And as we did last time， both you could use either of these update rules。

 they give you slightly different analyses。😊，Not important， I'll stick with hedge。It's very key。

Be good。😊，Good。So what I'm going to do is let me just prove the hedge guarantee for you。Again。

 it will remind you of what's happening and then we'll run with this guarantee。Okay。

 so I'll give you the proof of hedge。Look of this tale。Fair enough。

So in order to prove the stadiumum。What should I do？O。So let me let me again。

 you know and again this will come down to the same kind of analysis I'm going to track the potential I'm going to say what is the potential at time p plus1 it's just the sum of the weights。

😊，At time T plus one of all the widths。Overall， the experts。When this I know。

 I know exactly what this this quantity is， this is just WPI。😊，Times x of minus epsilon times L。

Over all days。Okay。😊，对。No。Comes the question。Of what I should。So I want to use， you know。

 all the game is going to happen in approximation of one plus epsilon e to the epsilon。Oh。

So I'm going to use， let me just write it down here， I'm going to use the approximation。That。

X plus minus z。Is less than equal to。1 minus Z。Plus z squared， let's say。F。They belonging to。

Minus infinity。这么不容易。So this is at last。ダには。1 minus epsilon LI P。Plus。Epsilon squared Li。嗯。Square。哎。

Good。Now。Here's one thing I can do。All my losses were between thereon and oh。

So I said my loss is between0 and one， right？😊，In fact， let's even say my losses。

between negative one and one。The same analysis we go through。So， let's see。So this quantity。

They like no steps one squared。The losses are between negative one。So this is at most。WRB。

1 plus epsilon squared。Plus。Snation。Epsilon times。 Okay， minus。Epsilon times， W PI。L。嗯啊。

This term is there。This is just one plus epsilon squared I've just pulled it on。ok。Okay。What is this？

😮，对谢。😊，Fly， thank you。Minness。Let's look at this guy。How does W relate to P？😡，What。嗯。

So how do you go from W to P？You agree on this。And what's the normalization constant？

 you don't even you， too close， stepping back， it's fine。So this is epsilon times why。Bi。

Say that again， oh no， so so I still I'll write down the English product， Let me write down the。😊，呃。

BT and。That's。Exbspsilence， great， thank you。So now everything's got 5 T。

 so let me just rewrite this thing cleanly5hi T1 plus epsilon squared。😊，Minus。

 and maybe I don't want。Bance of that。1 plus epsilon squared minus plus epsilon times。哔啲。So far。

The algebrabra will finish， it's pretty much again one of those things。😊，Which is at most。

And now I can use the E approximation。😊，Whi is one class x if less than equal to me to bes and this is for all X I don't even need to worry about it。

😊，So this is x most。b啲。Expo。Epsilon squared minus。Aon冰冰。亮点。对。So。Therefore。What there saying。

With the potential。At time。Capital D， let's say， capital。点。いい声と。How much？Actually， you know what？

Okay。I did an approximation that I could have done differently。

Do you guys mind if I go back and change things a little bit？Not to buy， I assure you。

This epsilon squared La quantity squared。Instead of bounding by epsilon squared。

 let me bound it by epsilon at times。Ay。And now let me not， let me go back to zero。

So I'm just saying this numbers between0 and 1， their squares are smaller than the numbers themselves。

So instead of， so now I have Epsilon LIT， Epsilon squared LIT。Well this guy， okay。

Minus epsilon minus epsilon squared。There was an epsilon squared sitting there that's become this。

Minus。Abspsilon thanks one minus。Minus epson。Minus absolute。我先信。No。Nothing much is happening there。

 so the important thing is look phi T plus  one divided by 5 T。😊，Is this quantity？

Phi T plus 1 divided by p T is at most this quantity。😊，So it's like a telescoping。😊。

So I want to say phi capital T。I at most。X of minus。Epsilon times1 minus epsilon times sumation。必定。

They'll just multiply。What。I'm sorry。Oh fine one， good perfect balance。Thank you。对了。

So this gave me an upper bound and phi1 I know is。And。And Captain。

But I also know that5 capital t is at least again the same argument as before it's the weight of the best export so far or expert i let's just fix expert I so it's minus epsilon times the loss。

😊，Of expert。The total loss of expertise。Which is just， you know。啊。X。Of minus epsilon。

Submission over times D of E I and anything。Sure。By hate。

This is the amount of weight that expert eye has at the end of the process。Oh。

And now I just take logs， there's nothing more， I'm done。So know。

this quantity is at most that quantity taking logs。I'm going to get。地京。Logs。

 I know negative epsilon times one minus epsilon。Thanks submission。B点 and边。Is less than equal to。

Is greater than equal to negative of。Plus。Lge n is greater than well call the negative epsilon times sum。

嗯系。那听。And I just do some exchange divide out by epsilons。Remove this epsilon， put an epsilon there。

Divide back once。And now move things around。move this to the right， move this to the left。Re。有有对。

A that most。1 over one minus epsilon。Im sum。嗯拜系。And thanks。B。罗嘅。Over that1 minus0。Yeah。And now。

 I'm doing a little。hand wave reaction I want to say this is at most one plus epsilon approximately if epsilon is less than half then by fidling around with the constants you can make it one plus two epsilon not important and this is you know I want to ignore this thing maybe put a two over there。

Again， absolutely that most half， none of this is really matter。

You can be a little better about this thing， but I you know， as we can see I hate doing these things。

😊，So yeah， best done privacy of your offices。But but you know， at least you know how to do this。

 if I can do this on the board， you can do this。😊，啊。

That's it you you just almost following your nose and you just have to figure out oh at some point I need to take a I need to approximate the exponential by a polynomial the first two terms just a simple Taylor series kind of thing。

😊，And then at some point I'd go back to exponentials because they're nicely compose。你解性了。

This whole thing， I mean， the advantage of using exponential out here was that once you multiply these together。

 the summation goes into the exponent。😊，That's exactly the term we。

What should you take away from this just that you can do it？You can do it under pressure as well。

 that's not a problem。You're forgetting， you just read it right。Good。

 and it's a simple analysis and it gives you this guarantee and you know so far it doesn't look that impressive。

😊，But its it's pretty d awesome。I still have to give examples of places where I've used this thing。

 I have a couple of examples in mind but will come to pass。😊，嗯。Okay。サベリトですね。嗯。

So let me write down a version of this theorem that's kind of oh。O。Slide， slide waveient of the sky。

Suppose。Losses。LDI。Belongg to negative 11。Now losses can be negative。

 which means they're really gains。Okay。😊，Then。You can get regret。At most， this epsilon T。Plus。

logganのがで。谁。😊，Notice that here we regret。😊，Was。Epsilon times the best export of us。

 which could be much smaller than three。Of course， we approximated it upper bounded it by Epsilonency。

And this was an upper bond， it's a gross upper bond。In general。But。

If if you want to get negative losses， you might need such a。Okay。😊，滚。嗯。

So if the losses are between negative one and one， essentially I can derive the same thing for gains now I have。

Games。啊。GI店。Between11 and one。I can get again regret is can be defined in the same way now what do I want to say I want to say GT。

啊。PPGP。It is at least one minus epsilon tile summation E I VP。Plus， oh， minus。老嘅我吗。

This should not come as a surprise to you， I can just call negative of loss again。Nothing's happened。

1 over day。1 over two， this is the average gain of the best export， this is my average。I at most？哦。

I can have a similar course。This is， I should have said。热爱。G闭。Minus epsilon t， minus loggan。我本他不知道的。

This is the same thing， regret is the same quantity。If I'm。If I was dividing out my time。

 this is just average regret。Then this whole thing gets divided by P as well。

Nothing's happening again。So this says。That average regret。Is at most。Abspsilonte。

Plus log n over epsilon T， so I'll say it's at most two epsilon。If。Pak is bigger than。

Log in over everything single square。Suppose T。Was bigger than login over Excelon Squared。

So log n over epsilon squared is going to kill this log n over epsilon turn。😊。

And I'll be left with an Epsilon。So this thing will give me an epsilon of us。

And this is epsilon t divided by T that's epsilon。😊，对。Okay。Moral of the story after enough steps。

The regret becomes the average regret becomes smaller than two e。对。It's just a convenient packaging。

And once you have this packaging， for the rest of the lecture， I'm just going to use this packaging。

The average regret is that most， let's say two epsilon if t is smaller than this sky。Good。

One one final change。Losses were between gains were between negative 1 and 1。😡。

Suppose gains are between negative。呃CNC。What changes？How would you play the game？

The gains are now between negative C and positive C。

So we will keep it there gains between negative C and C。对不对。What should I do？Yeah。

Normalize divide out by C， right？😊，And if you just do the thing。

 you you'll realize that you know these terms will get multiplied by a C。😊。

And really all that change is you' will change this thing to C squared。

We are really you know in order to get epsilon loss。Now you need epsilon over sea loss more or less。

😡，Epsilon overseas， epsilon squared overseas squared C squared goes up。Some some little calculation。

え。啊。That's it。Just keep this in mind and we'll go on for the rest of the lecture。

Sometimes this C is called the width。对。This， some job' ago。I will keep it there。Questions。做发设备。Okay。

So let's use this to solve something interesting。😊，Let's use this to give a strategy for zero sum。不。

So I have to define what zero sum games are for those of you who don't remember who haven't seen it before。

😊，0 some games。What a zero sum game？So zero sum game is。It's one of these things。

 so it's given by you know two players， so it's really two players I should say this but。😊。

It's always implicit， two players。嗯。Od。And see， think of row and column。Okay。嗯。So the role player。As。

M strategies。OfM actions。The column player has n actions。Now， if。Our place。I and C please。ジ。

So I is between 1 and M J is between 1 and n。Then。啊。没有。哦。R is equal to Mj。Pa off to C is negative a。

MIJ is the number。This much of money goes from C to R。😡，M could be negative， which is this。

So it's whatever， if negative one money is going from C to R， then really one money is going from RC。

那行。O。😊，And the way you view this usually is you write down the matrix M。😊，If R plays EI。

Then it's like you are choosing the eye row of this guy。

And you're choosing the JF column of this guy。And this is how much money is going from C to R。

How much money going from R to C is just a negative thing this is way it's zero sum。

It's not a general game in general games， you have two matrices the pay off to the row player and the pay off to the collar player or you have two numbers sitting out there。

It could be the case that oh， both of them get a buck or both of them lose a buck。And this is like a。

Rock paper six years。Somebody when somebody loses。By normalization， we could always imagine that M。😊。

Is in negative 1，1。Build the M号。All numbers are between negative  one and1。

This is some normalization I'moid。点。😊，If R play the singles action and C plays the single action。

 these are known as pure。😊，Strategies。You can have， so these are， you know， if R and C play。

Single actionss。This is高了。Pure strategy。But what R and C could play？

I they could play actions which are just distributions over things so the usual example is the usual examples the usual one right okay so let's call this left right left right this is the kicker。

😊，And this is the。你跟我连。And we are playing soccer out here in case you were wondering。

 so if the kicker kicks to the left and the goalie also goes to the left。

 then the money to the kicker is negative one。😊，They don't make a goal， otherwise they get a goal。

 they get a goal， they don't get。😊，And now of course， there is this sort of issue of who goes first。

 who goes second， what happens if they play simultaneously， etc。And in fact。

 you want to imagine them playing simultaneously and you also ask questions like， oh。

 what if the kicker goes first？😊，et cetera， so what you know r andC can decide to play what they call you know randomization so r plague a probability distribution。

😊，Over its actions。C plays a probability distribution。Over her actions。Then。

These are known as mixed strategies。Of course you want them， you imagine them playing simultaneously。

 but they can fix the strategies beforehand， they can say 60% I'll go left 40% I'll go right。😊，行。

Mix strategy than the expected payoffs。Is P transpo MQ。P andq are column vectors。

 so p transpose N q is a number scalar。That's the expected pay。

 it's just exactly what you think it is， right？But one and J， this guy plays I。

 this guy plays J by y。😊，Okay。😊，来了。Good。I'm writing all this。

 but then I have to cover it up so let me be parsimonious and I'm going to do the horrible thing of making little boxel when。

😊，Wing inside them。啊。Good。So let me define。The column clear best response。Do aB。

So the row player decides to play action P， the column player's best response。See。

 the column player is trying to minimize so this guy this is expected payoff。😊，To R， I should say。

 the expected payoff to see the negative of this quantity。

You know it's just I'm just telling you how much money is going to go to our C's objective is to minimize this quantity。

 so C's best response to this should be minimize overall Q。😊，Of P transpose m。Best response。有病。

Similarly， best response to Q is the max overall pay of pay transpose mQ。

Best response of the role player。To a particular queue。Back。For all P and Q in the appropriate sets。

 you know， P and Q are in the appropriate section for this。

 I'm never going to write all these things。嗯。What can we say， we can say r of Q is at most C of P。😊。

咩。😊，Should we prove this guy？Let's prove this guy it's like a domain man right。In fact。

 Im want to prove this。Out of view。So for all P and Q， I'm saying r of Q is that c of P。

 hopefully this is correct， well say you know proof。😊，R of view。

Is less than equal to the max over all。Be prime。Of be prime。Pranpose M Q。

Because this is one particular。😊，嗯。对。R of Q， sorry， I don't know what I just did R of Q is the max。

 it is the max。Overall， B。啊。😮，offff。What am I doing？I've lost my chain of thought just for a second。

The prime。Of the prime。MQ right。This is definition。This is less than equal to okay。林心好嘅听。啊啊。

Let me check。I should have some。Jing north O test。I don't know what I'm doing。

I've lost my you know what， maybe this is a good time， let's take it to my。

 let me collect my thoughts。😊，So how do we prove CP is less than equal to2？So， let's go back。

B B is equal to name。Overdue。Of free transport and Q。Which is less than equal to。It's you prime。

Which is less than equal to p transpose Mq。Because this is minimization。

Which is less than equal to max over the prime。A good time to you。你最接可点呃养。You're absolutely right。

So in fact， I was claiming something and I was boldly claiming that this was correct。

It going forward bit。The opposite is。So much， you shouldn't believe me。

You should make me prove all the theorems where I say， well， you know， well。

 of course this is true trust me， don't trust me。😊，再练练。The column players。 so you know。

 this should make sense and let's let's go back and instead of。So the column player strategy。Okay。

So what's happening？Let's let's， let's do this。What is CP？The role player is fixing its strategy。😊。

And think come on call play， give me your best response。The kicker is fixing their strategy。😊。

And he's saying， oh， what can you know， what is the。What is the best response？Of the goalie。

The kicker is deciding first， right？😊，The goalies should have an advantage。

 they know the kicker' strategy。The payoff should be less。Okay， this makes sense。

 I was just confusing myself。Yeah。Because remember， this is a payoff to us。So if。

The row player goes first， their payoff should be less when the role player goes second。

This is our natural direction good。So， now。呃onments。What塞。😊，Sorry， say it again。有的。几百的那个。

So the theorem will be that。You know， one can fix strategies so because it's a zero sum game。😊。

You can actually come up with strategies for the。Kicker。But the strategy， the mixed strategy。

 so it's not like oh I'll always go left or I'll always go right。I'll fix a strategy for the kicker。

😊，So that even if the goalie knows the strategy。They won't have an advantage。

So in this particular game， for instance， if I told you I'm going to go 50，50。😊。

You have no advantage。And it's important that this is like a fraction strategy。

 this is like a mixed strategy。😊，Because if it were pure strategy， if I said I'll go left。

 you will be like do。😊，You人你。 so the fournas， the mini max theorem says that。Actually。The。

Max overall， B。哦。We have to be。有咩改度。有你攞我知。So one direction is immediate not immediate I had to s for it but。

But one direction we know now。The Tem is saying did exist B Q。So in particular。对 blank， did it exist。

ピエキをさしたスティーオピー。Is greater than you。嗯。So for each am there exists these things。

 so given any am and this is important that this is a finite。😊，ze手表。

This is not necessarily true for infinite basis。You need to assume something。

 oh it's a concave convex game or something like that and then what is what's the theorem called seaion theorem or something like that I forget。

But。This is the finite games you'll be able to prove this。And really。

 what I'll show you is I'll show you， you know， you fix a game then for。

For every epsilon there exists PNQ such that this is bigger than。

But every epsilon positive was happened。So there were a gap to the nepsilon smaller and then show you that I can be。

哎。来了讲个屁。So this is what I'm going to prove。Good， and I'll give you an algorithm to find this。

Questions。Yeah。Maybe I'm are we missing something from our definition of a zero game I need to have an equal number。

 negative ones and warnings。嗯。对。So then that it's possible， we all want absolutely so in this case。

 so suppose the matrix are all ones。Then this is saying no matter what the role in column play do。

The column player always gives a buck to girl。Yeah。

 so the equal number is implicitly coming because I've just defined it this way。😊，有。Other questions。

Yes。So let's give an algorithm to find a pair P and Q which satisfies this property。

So here's what we do。Okay， so let's go back to this picture。

So there are n strategies for the role player。And strategies for the current。诶。

I'm going to do the following。I'm going to。Maintain a probability distribution。异地。one。Up to P T N。

On the roads。So at every point in time， Ill have a probability vector for the row。So at each time。

And beach doneB。B地。Is the probability vector。On roads。诶。So basically， the al。嗯。The role player。

Please。你的。The column player。咩s。Best response。哦。哦。PT transpo。对。Thank you。

The role player is maintaining a distribution overall。It's going to play this sector。😡。

The column player says， well under this probability distribution。😊。

What's my expected loss for column one？What's my expected loss of column two。

 what's my expected loss of column n？It's basically given by。This vector。

This is just saying I'm taking all these columns。😊。

In proportion to the probability and I'm summing them up。That's going to give me， you know。

 it's just summing up the rows this way in proportion to the probability。

So this is how much it expects to lose if it plays action 1， action 2 up to action。So it will play。

So what it will play is it'll play action。Jab key， let's say。Which is the a。咩。啊，这样。哦 b。Gos suppose。嗯。

He'll play the action， which is the best response。本啦。So the role player is playing according to the。

Will some probability distribution the column player plays accordingly？😊，And then I say loss。Do the。

Lastね。Actually。😊，I'll say gain vector， this is a little， you know。

 sort of weird and I'll explain in a moment。Game vector， G P。Is going to be。嗯。Times。你系。In。

What what's that quantity if the if the column plane this column？This action。This is my。G力。Okay。嗯。印度。

Hnge。唔嘅。嗯。对。At each point in time， the row players actions are just coming from hedge。

It plays column play， play best response。This gives me one column。Of this matrix。

I'll feed that as a gain vector， Ill get back a new probability distribution I go。😊。

Let let's look at an example。Suppose this vector had one sitting out here and had you know a low number sitting out here。

 let's say zero sitting out here。Coll and play is playing this。And suppose the it was 50，50。😊。

What would hedge now do？HedgeHedge would place more marks out here。Which is kind of a good thing。

 right？It will take into account that， oh， this seems like a good row。😡。

Maybe I should have played that。So the fact that I'm giving these gains。

Back to the back to hedge will increase the probability on the large entry。😊。

But let's see how how this was。Workax。At least if the algorithm and clear。😊。

I just have a probability distribution initially uniform， I don't know anything about this game。

I play a random strategy， essentially。The column player play the best response。I say， oh， you know。

 on this column at least the top rows look pretty good， the bottom rows look crack。

 I should move my mask up there。😊，Maybe I move my mask up there the next time the column player play the response out here。

 which is like negative one out here and maybe one out here and maybe this was like half out here。

And maybe this is still there。I said， oh， I put a lot of mask here。

I shouldn't have put all my mask out there because now it looks starts to look bad。

 maybe I should start moving my mask into the mat。On average， I should even know。

And we'll see how how this playsazs out in this arm。But is the algorithm东西。

Row player playing hedge column player playing best response actually we could have both of them play hedge that would also work。

If two of us play hedge， we will both converge to something which satisfies no regret。

And you should really think of this as being the reor， that's when it's going to come。Yeah。对。

I want to play this or。These steps。And T is going to be at least log of m over epsilon squared maybe four times this you know。

 not important。なの。This number should really be that number。Regret should be more。O。

And then now define he hat to be there。Some of people over here the average plate。

You hack is the son of EJ。No don think the average。My claim is that P hatt and Q hatt will satisfy。

Right with maybe a constant enough， Andy this will be programs along or something。

Does the general strategy make sense？We'll see how the proof goes。Is the strategy clear？Yes。So。

 so JT。Is the best response？To be。That's allで。open to a matrix。And it should be like a vector。

 so this is like a vector。And I'm choosing， so this is like a robotic， you know。

 if you look at PT transposen。😊，P transport them。I is like， you know P1， P2 p， you know。

 it's like an average of the rules， it's like a rule。I'm looking at the entry out here。

 which is smallest。That corresponds to a column。嗯那就不能。And really， you should think of this as being。

This is like the best response。有。对行。别人呢？And now it just comes down to understanding。The behavior。

Of this algorithm。So let's look at the behavior。So， let's。Look at。Let's look at R。あ不し了。

What sort you think？It's equal to。That's。你女。Maybe I shouldn't。对by。Let me let me go forwards。

 I always try to do smart things， make mistakes。Donation。嗯嗯对。

I'm just writing down the expression for regret。This is the average you。So this is the average game。

What is。The average gain， what am I guaranteed about the average gain。

 the average gain is going to be at least。1 over two times。The game。哦。Anynie。Particular。啊。Iike。电这个。

Minus。我也不知道。本。Is it equal to。你生。我为爱。哦。1 over8。Inner products are linear。小他。oh， sorry。

 sorry I'm summing over all times Steve。And this is for anyI。

The gain is as good as the gain of the best export minus2 epsilon50 is large enough。But the gain is。

 you know， these game terms are linear so I can push the expectation and the yeah。

 the average insane。V equal to。你爱。What is this quantity， how are the gains defined？M times E J E。

This is the gain at time T。Divided byて。What is this？M is just a matrix。

Smation of E JT over T is the average play of the column player。Oh。This is true。For each eye。

 so this quantity。Is at least。で。Or each boss本来。嗯。So in particular。

 this is at least this quantity for the maximum。😊，What is the maximizer of this quantity？

It's not here， think of this in terms of the R's and Cs， what is happening here？

The column player is fixing its strategy to be Q hat。I want the eye that。Maximizes this quantity。

Is the best response。For I， so this was true for every eye， this is for。Oh。So。

 if this is bigger than this for each eye。😊，This is bigger than that。

 So maybe I could have written this to be。😊，Max over online。Lackax over online。咩次嘅度买。max over。

Everyです。Okay。😊，So that this。Is at least the best response of  Q minus two epsilons。

We're getting that。Now I just need to show that this quantity is at most。是 your边啊，你家。

So what is this quantity？啊。😮，So let's look at this quantity。This is1 over p。transformation。你啲。嗯。你真病。

By definition。The game vector was MEJT I could have even。We written back in a minute。

Let's look at this quantity， what can you tell me about？This。a。It's very similar to this。

 what is this one？What was JT JT was the best response。To pity。So this quantity。Is equal to 1 over p。

 the column player best response to peak。Just's just think about this。This is PTM。Is exactly this。

Combination of roles that I took。EJT was the best response。

So this is really just the best response of the column player to people。

So I'm taking the average out here。And now。I use we just prove this thing。But this is at most。

This function is。Go and give。So， the average。Of the function in that most the function of the average。

你。The average of the function values is smaller than the function at the average point。

And this just comes from the fact that C is defined to be the men of a bunch of linear functions。

NowWhat's a bunch of linear functions they all look like please。The min is the lower envelope。

It's gone Ca。You can prove this using algebra， but literally this is how。😊，And what is this quantity？

I's the average response。You have a response。Is at most is at least。

So CFP that hes out of Q minus2il。这个清你回答啊。诶 it over and then the the maximum can be good so you are asking for you know。

This is giving you so absolutely， you're quite right in the sense that this is just showing that there exists a good strategy。

😊，And now I could have chosen one of these guys who would be at least disc good。对啊。Offfhand。

 I don't know how I would make that work because what could happen is， you know。

 this is a standard problem with convex optimization。

What I could do in con optimization is I could get this point， this point I could。

Jump continuously between these points。Their average is pretty good。

But I don't know either of these points is not good。

So what I need is that I need a lemma which says something called last iterate conversions。😊。

Or that there should be somebody who at least is good if things were linear， we'd be fine。

But since things are convex concave， it's not completely clear。So we have to do a little bit of。Work。

😔，Right now， all I know is that this quantity is getting better。The average is getting there。播放首歌。

Now， in summary， CFfP is at least this quantity。Which is at least out of human students。

But let me just write this seal we had。Is at least auto。要。妈你。Which is what we wanted to show。Let me。

 let me tell you啊。The general， you know， so if you want to use experts so so let me give you a。

One more setting where。And this will be a high level explanation of how to use。😊，Experts。

I want to solve a linear program。And here the linear program all solving。Many miles。

The cost subject to。啊。Actually， let's maximize。The value。subjectubject度。

The size transpo x is less than equal equal to 1。Here's the vector。Of values。

Let's say the value are non negative。没回来。Excited on。So this is just saying maximize。B I， X I。

 such that。F I X I is that next fine。It's either non negative nature。How would you do this？

One constraint， one objective function， everything not negative。欧鱼。Really。喂。So this just says think。

😊，I such that V of an an Maximist。对。X sign one over that time。Readally。直播咗声。です。我 doing it的。

Startt them reading。This is an abstractack。You know， sorry。That's back。

B 1 over S1 is at least V2 over S2 with at least Bn over S1。Take one unit of this， one unit of this。

 one unit of this。UntilUntil you use up all your budget。This's just not。These are trivial problems。啊。

My claim is。Like solving LP is pretty much this problem。So let me get you away。

What do you want to solve？You want to。Just for the moment， think of matrixre。Constraints。

 which are all non negative。Okay。I want to solve maximize V transpo x such that ax is at least1 x is or ax is atmost one x is at least about x。

Okay。😊，Let's do the formula。I'm going to say。そそ a is some matrix like this。So here's what I to do。

I'll take the probability vector P1 p2 of P21。I'll maintain a probability distribution over the rules。

喂。😊，And this is going to change over time。Just the same example， for better。

Initially they'll start off at the Uniicor distribution。

 I don't know which constraints are the important constraints。At each time。Is time。

Define alpha P to be equal to。bady。Fンポ a。Beta K is equal to P。Tspo。Oh。Let me say X。Okay。😊。

What did I do， I took all the rows and I squed them down into one one one row。

I took the right hand signs。And I also averaged them out with him。哎。Now， notice this。

That the optimal solution so。If x star is the optimal solution out here。

Then X star also satisfies alpha T。Transpose x star is less than equal to beta。

X star satisfied each of those constraints。😡，So it satisfied an average constraint。か。

Here's what we'll do。So at teach point in time， I'll construct an average constraint。😊。

I'll call this the average right。It has a feasible solution because the same solution was out there。

😊，The original solution is still a feasible solution now it's got more crappy solutions as well with its one constraint earlier we had M constrain。

😊，Yeah。Let's solve so now。Solves so this will define this， define this， now solve this。

 maximizing de transpos。I'm solving a linear constraint， one constraint and a linear objective。

I kind of know how to solve these kind。😊，We are like up sector products。They're EV products。Okay。

I'll solve this。So solve this。Get back。Excellent。It's some solution。

Its value will be at least this guy's value。Because X star was the solution， so it's value。

In at least we。Tran suppose。Next time。Because the X was a solution to the same system。

So I'll get an even better solution。 Of course， this is like a completely bogus solution。😊。

It's got nothing， it's not satisfying all the constraints。

 it's just satisfying some average constraints。哎。不。Now， define。What do I want to do？This solution。

 if it satisfied all the constraints out here， I am done。😡，Because it has amazing value。😊。

And it sifies all the constraints， I mean corn better than optimal not possible， so it's optical。

So it doesn't satisfy some of the constraints。What should I do？

I should put more probability mass on the constraints that would not identify。

I should tell somehow the next average should have more of a constraint that is not that。😊。

Because those are important constraints， my solutions are not finding those constraints。

I should move more probability mass， let's say only the first constraint was not satisfied。😡。

Next time I should force。This， this solver to solve more of constrained world。

I should put more mass on constrained one。How will I put more mass and constraint one？

What language do I have？I have kind of multiplicative weight hedge。I should say hedge。

 put more mass and probability masks over P1。😡，How will I do it？How do I give input to H？

Through the game vector。I should have more gain on row one。If I wanted to put more mass in robot。そう。

Theyfin G。To be。What。😮，诶。X minus B。A should have been less than equal to be。

Ax minus b is how much I'm violating the constraint pie？A large game。Even if I'm violating it by lot。

If there's a large can， I'll put more mass on that the next time hedge will put more yeah next time hedge will put more mass on that。

 this solver will try to solve that a little more。And the process goes on。And then you can see。After。

P， which is at least。Some constant squared。Times log of number of constraints over exilon squared steps。

Have。LP solution。Which will be some X tagag， which will be like a。Average solution。That is fine。

V transpose x hat with at least v transpose x star because it's an average of a bunch of solutions。

 each of which is super optimal。But。嗯。Exat。Is less than equal to。B。是ます。

It's not satisfying the constraints up to Epslow。And you can make Epsilon this morning。

It's just in the running plan。OkayOne last piece and then I'll stop what is C sees this width term。

Which is， you know essentially how bad， how large can these games be？So you just figure out。

 you know， you try to control the width is the max over this this quantity。AX minus B。你识。

So if you can control， if you can do all this controlling this bit， that's very good。

And that's where all the action comes that with some of the fine tu， but at the first cut。

All you are doing is the following you are taking。An average constraint， you're solving it。

And you are saying this average constraint doesn't quite solve the problem we are interested in。

Let's rewa and resolve。嗯。And as usual， I've gone a little over time。

So I was going to show you a little。Experiment。So here is is the here is the way you want to solve Max flow。

 right？😊，So the standard way of solving max load is residual graphs， you figure out you send flow。

 you send we put in the back edge， things like this。😊，Here's the way to solvevent。

Find the shortest bucket， every edge at weight length1。😡，Find the shortest box。

Increase the weight of edges exponentially。So every edge which got a weight of  one。

 its so every edge which got flow in this shortest path now has length  one plus epsilon。😊。

Find the shortest part。Increase the weight by one plus expsilon factor again。

Another short respond and so on and so forth。This algorithm is just implementing this thing and we'll do that next。

😊，And now you can show that no need for residual graphs。

This process will converge to a max flow in time。あちゃった。

So this is this is very sort of acute little algorithm and maybe I'll put the Python code because I wrote the Python code myself I feel proud so I'll put the Python code and pi you guys can play with it and see what you think。

😊，In any case， have a good weekend guest， and I'll see you on Monday。

