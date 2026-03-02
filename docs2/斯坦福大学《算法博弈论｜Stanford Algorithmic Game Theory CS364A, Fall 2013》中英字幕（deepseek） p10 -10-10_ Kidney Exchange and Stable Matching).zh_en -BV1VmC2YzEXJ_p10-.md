# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p10 -10-10_ Kidney Exchange and Stable Matching).zh_en -BV1VmC2YzEXJ_p10-

So the topics for today， this will be our final day on mechanism design。

 and we'll be talking more about mechanism design without money。

And we'll be doing a case study in the first part of the lecture that will be on kidney exchange。

 and I would be remiss to not tell you about stable matching。 so that'll be topic number two。So。

Kidney exchange。And sort of a great application of mechanism design without money。

Just over the past 10 years or so。So there's a lot of people with kidney failure out there。

 So There's a lot of people who could really use a kidney transplant。And an old idea。

 which is not specific to kidneys， But you know， applies to all organ donation。

Is that you have deceased donors。 Okay， so I and probably many of you have that orange dot on your driver's license。

 which says， yes， you're going go ahead and donate your organs。

But there's something special about kidneys。Which is， we have two of them。And generally。

 we do just fine with only one。Okay。So if you're living。

 donating a heart isn't usually much of an option。But donating and a kidney is。嗯。

So there's a notion of living donors。When it comes to kidney transplants， and so think about。

 you know， someone's spouse， someone's sibling， et cetera。

 who's actually happy to give up one of their kidneys for a loved one。Alright， so there's a problem。

 though。 Sometimes it just works out。 Okay， sometimes， you know。

 just your spouse or your sibling will donut。 you a kidney， and everyone lives happily ever after。

The problem， though， is that it is not the case。That anybody can really successfully have a kidney transplanted from just anybody else。

There are compatibility issues。Yeah。The blood type。Is a big one？Tissue type also。

 these are the two first order issues that determine whether you're compatible or not compatible。

 So for example， if you're a patient with blood type O。

 then you really need a donor who's blood type O if you're a donor with blood type A B。

 you really need a patient with blood type A B。 and that's not the only issue。

 but that's one of the main issues。So that can be a bummer when the people who。

Are willing to donate a kidney to you are incompatible。

So here's an idea which started occurring to people。

 or at least that started getting executed toward the beginning of this century。

Which is suppose we had the following situation。We have a patient。

So someone who needs a kidney and they have。I loved one who would be willing to donate a kidney。

And they're incompatible。So let's say for concreteness that this patient has blood type A。

Whereas the donor has a blood type B， so those are not compatibleible。

But suppose there's another pair。In the same situation。A patient， a potential donor， incompatible。

 And the patient here has blood type B。And the donor has blood type。

And these superiors of people generally speak and will have never met each other。

But if they knew they existed。Despite the fact that they naturally showed up in these pairs。

It seems like it might be a really。Productive idea。Two swap donors。

Even though you have no idea who they are， even though you never met them。

So the donor from the first pair could just donate compatibly to the second patient。

 and the donor from the second pair could donate compatibly to the first patient。Okay。

So this is what's known as kidney exchange。Yeah。So around the beginning of this century。

Kidney exchanges started happening just isolated cases。

 kind of lucky ad hoc occurrences at a couple of hospitals。

 I think Johns Hopkins was one of the early pioneers。 And， you know， they worked great。 I mean。

 lives were being saved。And so then the obvious question is， well， you know， if。

 if we can do this and we can save lives this way， you know， why don't we want。

 we want to make sure that everybody's aware of all of the incompatible patient donor pairs out there。

 So you want， in effect， a quote， unquote， market for these pairs。

 the sense of awareness of who else you could be matched with。And so， you know。

 a clear question then that people had to think about10 years ago or even a little less。

Was how should you organize？Ideally， a nationwide kidney exchange。

 some kind of database where everybody iss in this situation。 A person who needs a kidney。

 someones willing to donate they're incompatible。 pairs like that can go and register。

 And you can look for of matches across the nation。Okay， so in some sense， you want to create a。

 quote unquote， thick market with lots of people in it so that you get as many matches of this form as possible so that you save as many lives as possible。

 okay。So what I'm going to discuss today is some of the theory that was done right when people were beginning to think about how to answer this question。

 I'll give you a little glimpse about sort of what's been concerning people over the past couple of years as well。

 But the national exchanges were indeed formed roughly the middle of last decade。

 And these are done now regularly。 So there are algorithms which find matches that are run periodically。

 I I had trouble finding the exact numbers。 But I'm pretty sure it's thousands of transplants a year are done because of the algorithms and the mechanisms that have been designed for these national exchanges。

 this is a big deal。Now it's not an accident。 I'm covering this case study and our week in mechanism design。

 without money。So， at least at present。Any kind of compensation。For organ donation。Is illegal。

In this country。Yeah。In fact， in every country， except。I'm not sure exactly why this is， actually。

Except in Iran。And while the waiting list for kidney transplants is roughly， you know。

100000 people now in the US， there is not a waiting list for kidneys in Iran Okay， because you can。

 in fact， buy one legally there。 there， of course， there are black markets， other places as well。

 but it's completely legal market in Iran。You can have an interesting debate， you know。

 maybe with your friends over dinner， you know， either either speculate or argue what's morally appropriate。

 You know， fast forward 10 years from now， it's not obvious to me this will still be true。

 It's not obvious to me there will still not be a monetary market in this country。

 I think it's an interesting question。First question is like whether or not you believe there should be one。

 Second question is just， you know， place bets will there be one。O。So I'm going to touch on。

Two early papers， meaning a little less than 10 years ago。by Al Roth。

 who's now here in the Econ Department and won the Nobel Prize in economiccons last year in part for these contributions。

Along with the Sunmaze and Unver。And so the first idea。When so in the first paper in 2004。

 these were ideas they were having before they really started talking seriously to doctors。

 they were sort of just brainstorming at that point。And idea number one was to， in fact。嗯。

To have better matches between patients and donors。

 apply the very algorithm I left you with on Monday， the top trading cycle algorithm。

So I described that algorithm in the context of a housing allocation problem。

 which was the same phrasing that Shaplely and Sf used back in '74 when they developed the solution。

And the correspondence here is， well， before we had agents。And their initial house。

So in the context of kidney exchange， this is going to correspond to a patient and their donor。

 their incompatible donor。 That's like their initial house。

So in addition to the initial endowments in the housing allocation problem on Monday。

 there were preferences in that problem we were modeling preferences as totally ordered as a total order over all of the houses。

 So in this case it would be a total ordering over the donors and the sensible ordering over donors you would use as a patient would be dictated by your probability that that particular donated kidney would be a successful transplant in you which is what your doctors help figure out So transplant success probabilities induce total orderings over the houses I。

e。 the donors in the system。So the rest of the correspondence。Total ordering of houses。Okay。嗯。

Probabilities。Of success。And what I hope you remember from from Monday was you know。

 this was this algorithm where everybody proposes to their first choice。

 and you look for cycles and cycles are opportunity an opportunity to make everybody better off。

 case where everybody sort of grabs what they want more。 And as you go around the cycle。

 everybody has something that's better off than what they had before。😊。

So what you're really hoping happens when you run the top trading cycle algorithm in this context is you're really hoping for just sort of simple things like this。

 Okay， so you're gonna have a node。That's a P。And in this context， a node represents the pair。

 both the patient and the donor that are incompatible with each other。

And then you're going to have a second patient don't repair。And so the initial endowment here is D1。

 The initial endowment here is D2。 And but each one， right， So these are incompatible。

 If I'm using the same data as on this slide， these are incompatible with themselves。

 but each is compatible with the other donor。 Okay so certainly。

 this node has a preference for this initial endowment over its own because donor D 2 is more appropriate for P1 than D1 is and vice versa。

So in the first iteration of the top trading cycle algorithm， whenever you say to everybody。

 point to your favorite house， I point to your most compatible donor。

 you just get this nice little two cycle。And the top trading cycle。

 Im to then just says execute the swaps。 Okay， which just basically says donor D 2 goes to P1 and donor D1 goes to P2。

Okay。And one thing we did note， we said a few things about the top trading cycle algorithm。

 But one thing we said is that at least everybody winds up as well off as before。 Okay。

 so the worst case scenario for you participating in the system is that you wind up with the same incompatible donor that you started with and in the best cases。

 you wind up with someone that you're much more compatible with。All right。

So that was sort of idea number one， maybe we can just apply the top trading cycle algorithm out of the box。

So there are some issues with doing that。 And so let me tell you one that's sort of easily handled in the same model。

 And then I'll tell you about two others， which really motivated changing the model for the second contribution。

So in addition to just proposing。That tools for mechanism design should be applied to the need for a kidney exchange。

 And in addition to proposing that maybe the top trading cycle algorithm could be useful。

They also worked at the following extension。Which was they said， well， you know， actually。

 in the real systems， in the real exchanges， you don't just have these incompatible patient donor pairs。

 You also have patients that do not are not lucky enough to have a living donor。 Okay。

 so that would correspond to an agent who does not initially have a house in the housing allocation problem。

And， in fact， there's also things that correspond to a house with no owner in this context。

 You see what that is。Right， so a deceased donor right does not come along with some。

 you know patient that they're trying to say that they're incompatible with。 Okay。

 so that's a house with no initial owner that could be allocated to anybody。So， the extension。Was to。

 in addition to just the basic patient donor incompatible pairs， accommodate patients。Without donors。

And then also， deceased donors。Again， corresponding to agents without initial houses and houses with no initial owner。

And they showed that you could extend the top trading cycle algorithm to this more general setting。

 So in addition to swapping on chains， now， you're swapping sometimes on paths。

 Okay because basically， a house won't point to anything by itself。And so on。

And it remains dominant strategy and of compatible。 If you implement it properly。

 And this is a little tricky， actually。 So this is not。You know。

 if I had 45 minutes of lecture time to devote to it， I could go through it。

 all of you would understand it， but it's not just a trivial extension of the basic algorithm。

 You do have to do some work。One thing that was amusing was actually the algorithm that they used for this extension had already been worked out because it had been motivated by a totally different problem roughly six years earlier。

 which was that of assigning students to dorms。 So there is they wanted to use one of these top trading cycle like algorithms。

 but they had this issue where know， there were some students who say had been juniors in our seniors。

 their incumbents。 So you wanted to give them the option of keeping their current room。

There were new students， freshmen just showing up， so they didn't have an initial room。

 no initial endowment。 And then there were the students who graduated who left some empty rooms。

 you get had this sort of ecosystem of incumbents， people with an endowment。

 rooms that could go to anybody， and then people with no room。

 So that's actually the context in which this algorithm was developed。

 but then they realized it also made sense in this kidney exchange context。Okay。

 questions at this point。So let's talk about a couple other issues with this first idea。Okay。

So remember the top trading cycle algorithm。It people point to their favor remaining good。

 And then you get at least one cycle and you swap along these cycles。So in that example。

 it was a two cycle。How big could these cycles be in general in the top trading cycle algorithm。Yeah。

 you have no idea， right， I mean， you might just wind up with a Hamiltonian cycle in the very first iteration。

 It's possible。And in general， you might get long cycles， okay。

So that's just an observation we could have made yesterday。So fine。But now， so is this。

 why is this an issue。Okay。Well， to explain why this is an issue， Let me actually back up。

 Suppose it actually was just a parawise exchange。 Suppose we're back in the most basic case， P1， D1。

 P2， D2。So， and suppose we do the swap。对。So how many surgeries。

 How many separate surgeries does that entail this paraz exchange。4， actually。Okay。

There are two people you got to take kidney out of。

 And there's two people you got to put a kidney in。So that's four separate surgeries。Now。

 it's clear that， you know， a given pair， right， So， you know， it's clear that， you know。

 pairs of these have to be done simultaneously， right。

 So when you take the kidney out of this person， you're going to put a basically immediately into this other person。

 So those happen at the same time at the same hospital， for sure， okay。

What about the two different pairs， so what about P1 and D2 and then P2 and D1？

Can those happen sequentially asynchronously。Or you think that might be asking for trouble。

So something could go wrong if like you first did P1 and D2， and then like tomorrow。

It was scheduled to do P2 and D1。So问。Yeah， I mean， they might get on a plane to Chile， right。

 That's what you're worried about。 right， So you might be worried about reneging and。

It's really kind of， it would be kind of a double whammy， if that happened。

So the first thing which you might rightfully complain about is that in some sense， you know。

 P1 got a free kidney and D2 didn't have to donate。Okay。Which is， you know， seems unfair。

 But actually， the much more serious problem is that P 2。Did not get a kidney。

 Its as sick as before and lost its only leverage to be in this exchange in the first place。 Okay。

 so their sibling or spouse actually no longer has a second kidney to donate。 Okay。

 and that's really kind of a deal breaker。 So as far as I know。

 it's never been tried when you have these exchanges， these cycles to do them nons。

 as far as I know they have only been done simultaneously。

 So no one's even had the opportunity to kind of pull that kind of chna again。Right。So。

All surge is on a cycle。Have to be done。Simultaneously。

One thing that's sort of interesting is is actually。

 there have been chains being done recently just last couple years。 Also。

 One reason that chains have been happening is because of altruistic living donors。

 as they're called。 So sometimes you get someone who just， in effect， walks into a hospital and says。

 I want to donate one of my kidneys and save a life。And they don't have anyone kind of in mind。

And so with when you have this initial living donor， then in fact。

 they have done chains of even up to， I think，30 people。Okay， and that has not been。

 that is not simultaneous。 Okay， that has done sequentially over a month or two。

And if you think about it， sort of， if somebody renegs along this chain。

 the first issue we talked about before， someone getting a don kidney for free， is still there。

 But the second issue， which was the really serious one。

 which is someone not getting a kidney and losing their donor。

 that can't happen if you start with an altruistic donor。

 Okay so people have been experimenting with the sequential ones。

 But for the cycles they do it simultaneously。Okay， and if you， and so remember， you know。

 if there's K people in the cycle， there's going to be  two K surgeries。

 which have to all be synchronized at exactly the same time。 And you need a different operating room。

 a different surgery team for each of those， okay。Point being is you really。

 really want to actually have to keep these cycles short。So that's issue number one。So again。

 this model started coming about as the economists were talking to doctors。て。タ。

What are five different。全在で。It seems like that could affect。Your cycle。来前。It开。Yes， so theres some。

 So there's diminishing returns for having longer and longer cycles because of the reason that you say。

 So still in principle， you could have arbitrary long cycles。 But I'll get to this in a second。

 I mean， about exactly wheres the sweet spot。 How long should the cycle be And because there aren't that many types。

 There's no point in having super long cycles， yeah。Of the。Ting。Some。Absolutely， yeah， right。 So。

 I mean， really， I mean， this ordering is gonna just come from the doctor and that could be for everything。

 I mean， people will definitely travel for these， though。 I mean， that's sort of not， I mean。

 that's a pretty second order effect。 when you know， you've been on this list for a year， you know。

 and you're on dialysis。 I mean， it's kind of a second order thing。 having to travel。

 especially this is just the US。So， but yeah， I mean， all， you know， with your doctor。

 you would formulate kind of， you could use in some sense， whatever information you want。Okay。

That said， I'm actually now going to go in the opposite direction。And， you know， empirically， again。

You know， you started talking to doctors and how things really work。

 And you realized that actually this total ordering model is kind of。

Not the right model of preferences in kidney exchange。 I mean， really。

 if you're one of these patients， you just want to know， you know。

 is the transplant kind of probably going to work， or is it probably not going to work。

It's much better modeled as a binary preference， as opposed to a total ordering。 Okay。

 so empirically， patients exhibited and their doctors exhibited basically no relative ordering amongst equally compatible kidneys。

 so it's really to first order a 1，0 problem。So preferences closer to binary。Then total order。Okay。

 so。In light of this。So both to keep the cycle short and to really， you know， leverage these now。

 you know， this accurate， simple preference model， the plan is to use matching。Thank graph matches。

So let me explain。Any questions in the meantime。So a matching as I'm hoping。

 you know or picked up from that exercise set or what have you。

 A matching in a graph is just a collection of edges where no pair of edges shares an endpoint。 Okay。

 so they're all mutually non adjacent edges。So how are we're going to use matchings here。

 So what's the graph。So the nodes are just these incompatible。Patient donor parentss。O。So， like。

In that picture。A node has both a patient。An a donor。So that's the node set in compatible pairs。

And an edge just means between， you know， a given pair of pairs， if you will。

 It just means that we have the opportunity we have on that board。 Okay。

 it means that the first donor is compatible with the sufficiently compatible with the second patient and vice versa for the second donor and the first patient。

So you can do this kidney exchange with a good probability of success。So mutually compatible。

Noe pairs。So that's a graph， undirected graph told you the vertices have told you the edges。

So we're now going to define。The optimal solutions。 O， so we're gonna。

 we're gonna say what the feasible solutions in which of those we want。

 And this will dictate which kidneys get exchanged with whom。So a define。The optimal solutions。

To just be。The maximum Carinality matching。O。Which is， of course， you know， if you're using matching。

 this is the first thing you would think of。 You just want to save as many lap as possible。

 as many successful transplants as possible。Now， we're making a big assumption by saying the only feasible solutions are matchings。

It's an assumption which I've already motivated。The motivation was keeping cycles short。

So how short can cycles are cycles going to be if we look only at matching。Only two。Right。

 so remember， the， the matchings don't overlap。 Okay。

 so each of these corresponds to exactly that picture there in exchange between two pairs。

So by formulating it as a matching problem。We have restricted ourselves to pairwise exchanges only。

And again， you know， we are hoping to use mostly paralyzed exchanges。

 that's already for simultaneous surgeries。 I should tell you， though。

That if you look at the algorithms that are used now。

With these national databases to find good matches， they do not restrict to pairwise exchanges。

 They also use three way exchanges。 Okay， they look for them。Okay。And so why do they do this。Well。

 the main reason is is they just literally can save more lives by adding in threeway exchanges。 Okay。

 so the logistics are more painful， but they're not impossible。 And I forget the exact numbers。

 but you do really measurably better by allowing three way exchanges than with merely two way exchanges。

Now， the phenomenon stops there。 So people have certainly done， you know。

 run things allowing fourway exchanges， but the extra benefit from four or longer exchanges is minimal。

So it doesn't make a big difference。 So the sweet spot seems to be allowing two way and three way exchanges as people understand the problem now。

 in this lecture， I will discuss only pairwise exchanges。 we'll be using that matching model。

Question。都 say。He2。You also match with P4。你s么。If you met with a certain set of people。Yeah， so。

In the model， we will not make assumptions like that。

The model is just going to be this abstract matching model。 empiricalpirly。

 I'm sure there are correlations。嗯。And there are， you know， so。

 so sometimes when people have tried to get a finer grained understanding of certain issues。You know。

 including already trying to understand， I mean， so so this fourway match thing。

 the first represented empirically。 just well， we have the data。 Let's just run the algorithm， know。

 solve the integer program， get the best thing before it。 And it doesn't really matter much。

 After that， people sought out theoretical reasons for why fourway changes don't help。

 And then they really needed sort of more specific models about where the incomp incompatibility comes from。

 So they really said here， the blood types here， the frequencies of the various blood types。

 Here's the tissue and compatibility stuff。 And so there you get more sophisticated models of。

You know， because then you're really trying to， you're trying to explain phenomena that are kind of special。

To this application domain， Where today， we're really just gonna be talking about stuff you can do with matching。

 that this was the motivation。 And this was the basis， you know， I mean。

 when they were sort of first trying to think about how organized these things。

 this really was what they were thinking about。 So this was the starting point。

Is there any mechanism for。Excellent question。 So the question is。

 what if you come with not just one donor， but two， So maybe you have a brother and a sister。

 they'd both be happy to give you a kidney。But neither one works。 In fact。

 so I'm gonna state for the mechanism I'm about to give you。I'm going to state a DSS I C results。

And the DSA Sea result I'll basically to say it's near it's incentive compatible to report all of your edges。

 So everybody you're compatible with， you should just say。

 you should just say who you're compatible with。 And that easily carries over to if you have multiple potential donors。

 It can only hurt you to hide any of them from the exchange because those basically correspond to more edges。

 more people you're compatible with。Yeah， so I mean， that's how， I mean。

 the basic way they just handle is they take the union of the various people that any of them are compatible with。

 And then， of course， they're only going to match one of them。 Okay。

 so both aren't going to have to donate。Why do you ask？You're saying because they're doctors。

 maybe they don't incentivize or。T。That's right。 Who do you think might be more crafty about this。

 actually， the doctors， the patients。So the thinking is that， yes。

 it's important to be incentive compatibleible because doctors might strategize。

 That is the thinking。Good。Alright， so the model。Sort of already suggested what this might be。

So each node I。And again， you should think really， I would actually encourage you to think about this note as the doctor or the hospital representing this patient donor pair。

So each node， I。Knows amongst the other people in the pool。

 which ones it's compatible and which one it isn't。 So put differently in sort of the graph。

 each node knows its neighborhood。 It knows the incident edges。But it can report。

 or at least I'll use the word report。Any subset。Now， maybe you're wondering， you know。

 can't sort of the exchange figure out the same things that doctors figured out from the health information or something。

 But the issue is， you know， as a patient， and this is sort of in the law。

 you have a right to refuse any possible map with no questions asked。Okay。

 so if the algorithm says we think you should match with this other person for the following reasons。

 you can be like， yeah， I'm not feeling it。 I a bad feeling about this， sorry。Okay， so they really。

 you really could manipulate this， in a sense， prerejecting some number of your potential matches in the exchange。

 Okay， so think of that as under reporting your edge set。

You can't make up fictitious edges of compatibilities， Although that， if you think about it。

 probably wouldn't help you either。But in the model， we disallow it。O。And so， the goal。

Is a DSSIC mechanism。Of course。As we discussed， there can't be any money。呃。So that。I reports。

The entire set EI。Okay， and this extends that if you have multiple incompatible donors。

 we want to know about all of them。And again， remember。

 the other thing we want is we want to maximize surplus。

 which we're defining as having a maximum matching， matching as many patient donor pairs as possible。

So this is a sort of age old question for us in this class at this point。

We've seen many examples of DS S IC surplus maximizing mechanisms。 Of course。

 the difference here is that there's no money。 So there's no VCG mechanism。 And in general。

 in sufficiently general settings， there's impossibility results saying forget it。

 There's no way you can get both surplus maximization and DS S IC。 If there's time。

 we'll see a concrete example today。So the hope is that the problem structure。

It's sufficiently nice that we still can get both surplus maximization， meaning and max matching。

And DSSIC in this sense。O。So let me tell you the mechanism。

So I guess we know we have to try to pick a max matching。 That's one of our goals。So。Essentially。多少元。

Okay， so the node set， we know who everybody is。 We know who's registered in the database in compatibleatible patient donor pays。

We get reports。FI。For all I。Okay。Now， we just sort of take the union of all the F Ps and look at the graph。

Okay。Now， we want an undirected graph， and there's a little bit of an issue here。

 because for arbitrary Fs， it might be the case that I says， oh， I have an edge to J。

 and J says I don't have an edge to I。Which is tanmount to I saying， I would accept。A kidney from J。

 And J says， well， I won't accept one from I。 And then obviously， it's no go。 Okay。

 so both endpoints have to agree that there's an edge between them。

So what the mechanism does is it forms the obvious under the graph。Just of the edges， Ij。Such that。

Both I and J reported， reported its existence。And then。You know， what else can you do， really？

Return to maximum cardinality matching。Of G。Now， you'd be right to complain。At this juncture。

M points。That is maybe a little underspecified this mechanism。嗯。Yeah， that's very complaint。

I said there's only one max matching。 There's one max matching。 It's clear what this thing does。

And if there's more than one max matching， we have to make a decision。

 We've actually been lucky a lot。 or for a lot of cases where there are ties in this class。

 it didn't really matter。 And we'll have another example later in the class。 Here， it does matter。

 so we got to pick the max matching in sort of some kind of consistent way。All right。

 so which max matching。 So matchings， maximum matchings can be。呃，Not unique。So。

 there's a couple senses in which they can be not unique。And the first one， we don't。

 we don't care at all。 Okay， so the first thing is。You could have two different matchings。

 with different edges。That match exactly the same set of nodes。So here are two perfect matchings。

 Everybody's matched， but I pair them up differently in the two cases。And remember。

 we're assuming that patients could care less who they get a kidney from。

 as long as it's from someone with whom they're highly likely to be compatible。Okay。

 so we're not even going worry about the edges in the matching。

 We're gonna worry about the vertices that get matched。

 We could care less which edges are used to create the matching。So this is we don't care about。

That's at you number one。Issue number two， we need to make some kind of executive decision about。嗯。

Which is actually， you know。When you have a perfect matching， and clearly， that's the max matching。

 Everybody is matched。But when you't have a perfect matching， someone's going to be left out。

 and sometimes different matchings leave out different people。

An extreme case would be if you have a star。嗯。Patient one is set。

But then everyone else is basically playing the lottery。

 where only one of these other n -1 spokes can actually be chosen in a max match。

And we need to decide who。Okay， or we need to at least in our model， you know， figure out。

How we allow this to be decided。最。嗯。So you have to def。

 means even uniforming the set of all maximum matchings。嗯。Is it obvious that's DSIT？No。

 it's not obvious to me。s。That to make it not。Yeah， it's not obvious whether or not it's DSSIC。

 I agree。So that's not unreasonable。 But my only thing I'm trying to point out now is we need to make some decision。

 And it is the case that if we're completely careless for this decision， it's not going to be D S IC。

And I I'm going to just give you one simple approach that does lead to a DS SI C mechanism。

 There's no claim it's the only one。And in particular， I'm gonna do a deterministic version。

 which is pretty much the only things that people are comfortable with in practice in this domain。

I mean， in principle， I think you could be randomized。

 but that's sort of just not done in this domain。Okay， so。

So here is going to be the kind of solution。 And again， this is not the only way you could do this。

 The reason I signal this out is one， It's simple。2。

 it's pretty closely related to how hospitals sort of treat their patients in their waiting lists anyways。

 Okay， so this is maybe kind of minimum distance to existing policies。

Which is just a priority system。So up front， you order the nodes。And let's just reind the nodes。

 So the ordering is from one up to n。 The semantics here is one is the highest priority patient。

 You want them matched if at all possible， You know， then subject to that， you want two matched。

 subject to that。 You want three matched and so on。 Again， we don't care what edges are used。

 These are， these are nodes we're talking about。So how actually how do you actually implement these semantics？

Oh， I should say so， So hospitalitals， they actually do have patient priorities。

 They have like a scoring rule， which takes， you know， various properties of a patient。 for example。

 how long they've waited on the waiting list that boost your score Sometimes they take into account how rare it would be for this person to actually find a successful transplant。

 depending on， for example， your blood type。 you maybe more or less likely to be successful with someone else in the system。

 So they use features like that to formulate these priorities。

 And so they do have these prioritized lists。All right， so we know we have。

 we're going to output a max matching。 So let's just sort of initialize with everything we might possibly output。

So these are the max matchings of G。 And again， the interesting case here is when there's no perfect matching of max matching。

 actually， leaves a lot of people unmatched。 and we have to figure out who are the ones that get left unmatched。

 that's， that's the key case here。All right， so now we just go through。One at a time。And。

So let me just write this down。So in the first iteration， for example， you would say， well。

 are there any maximum matchings where one is actually matched。Okay， if， so if one is unmatched。

 if the most important person is unmatched in every single。Max matching。

 then there's nothing we can do。 Okay， we can't pick one that includes one。 Otherwise。

 we're going to funnel in on just those max matchings that do match。Number one。Okay。

Then we're gonna repeat。So in general， when we get the iteration I。

We have the matchings that are still permitted as outputs。And we say， well。

 are there any matchings in here where I is one of the match nodes。 Okay。

 so let Z I be those matchings。And there's two cases。So case 1， the happy case for agent I。

 is that actually there is a matching at our disposal in which I is matched。And if there is。

 then we will， from this point on commit to outputting at the end of the algorithm and matching where I is one of the match people。

So formally， we just set the sort of feasible， possible feasible outputs for the next iteration。

To be the matchings that were feasible to the previous iteration restricted to those that match I。

So the unhappy case， case 2 for Age I is actually given previous iterations commitments。

 There are no matchings left in which I is matched。So then we just say， sorry， agent and I。

 we have to skip you。And we just keep the same set of feasible outputs that we had last iteration。

So we start with all max matchings， and we slowly filter to a smaller and smaller set。

 It's always not empty。 We never let it go empty。But we make these successive commitments about which nodes are going to be in the maximum matching。

 And that gives us the sequence M0， M1， M2 up to M N。Because I forgot to say what we do at the end。

At the end， we just output any。Matching。From the final set。From M M Saan。So I't let to absorb that。

Yeah。So。主。Do those themselves have。通章。ちょこ。Yeah， saw I mean。

 the details here I don't really know about， I mean， in principle， sure。um。But， I mean， the。

 the things that I've seen that are the， you know， first order factors about your priority don't seem very easy to me to manipulate。

 So like how long you've been on the waiting list。And of course， the longer you've been on。

 the better your score， right， So the only thing you do is drop off， but it'll actually hurt you。

And then something like your compatibility information seems like you want to be honest about that。

 just so that， you know， the transplantpan itself， it's actually going to do the right thing， right。

there opportunities for like minor manipulation。 I would expect so。 But I think， to first order。

 I haven't really heard complaints about that so much。But again， this is not my expertise，O。

So that's a mechanism。 So again， the way to think about this is we make a sequence of commitments。

 At the very beginning， we commit to outputting a max cardinality matching。

 That's our only initial commitment。😊，Then we try to commit to outputting such a matching that matches one。

 Of course， if there's no way to do it， we give up on one。 Otherwise。

 we do commit to matching agent  one in our max part not only matching。 Each iteration， we say。

 given our previous commitments， is there a way to commit to matching agent I， If not， we skip it。

 Otherwise， we project to the matchings that also match I。Good。So if you think about it a second。

 all matchings in this final set match exactly the same set of nodes。

 There can be more than one element of M sub n。 There can be different edges。

 But the nodes that get matched by any such matching are exactly the nodes where you fill into case 1。

 And I'll let you think about that。😊，So， so it's a well defined output。

And I'm going to leave it as an exercise。prove that it's DSSIC。Okay，It's not too hard。

 but it is it's slightly tricky。 So I'm to ask you to go through that in the privacy of your own home。

All right。I got to say。This paper uses actually one of my absolute favorite theorems ever。 top 5。

 maybe even top three theorems I've ever seen， which is called the Gli Edmds decomposition。

 It gives just this。😊，Beautiful characterization of what the mass Carality matchings look like in an undirected graph。

 And I was so hoping I could find some excuse to like use some of this lecture to tell you about them。

 but which is too farfield。 I couldn't justify it。 But anyways， if you're feeling keen。

 maybe check out this05 paper and they actually use the Gidemans Glimans decomposition to implement in particular。

 some randomized variance of these priority rules that have certain properties。

 but it's's a super cool theorem。😊，All right， that's what I want to say about matchings。

 I want to say a little bit about kind of what people are worrying about now with kidney exchange before I move on to stable matching。

 So any questions at this juncture。是。Cutting edge。What are people worried about now。

 so I already mentioned the three way exchanges， so that's something that's done。

So the main thing on the incentive side that people are worrying about is。

Getting the incentives right。Not on the level of individual patient donor pays。

 but on the level of hospitals， because actually with these nationwide exchanges。

 generally hospitals are the ones responsible or that take charge of reporting the incompatible donor pays to the exchange。

 not the actual individuals themselves。So getting the right incentives right for hospitals。

And itll it'll be。Clear what I'm talking about if I show you an example。Two examples， actually。

So imagine there are two hospitals in the world or in the in the country reporting to this exchange。

H1 and H2。转。Each one has。3 incompatible donor patient payers。

And'm going to draw exactly the same kind of graph we were talking about in the matching case。

 So for pairwise exchanges。So let's suppose the compatibility graph looks like this。It's just a path。

On these six nodes。Okay。So again， the top three pairs belong to one hospital。

 and that one hospital is making a coordinated report of its pairs to the exchange。

 samee thing for H2。The main thing I want you to notice is both H1 and H2 have the opportunity to go ahead and do one of these parawise exchanges internally。

Okay， so for just sort of， you know， swapping one and 2 or swapping 5 and 6。

 These hospitals don't even need to report the existence of these pairs to the exchange。

 In some sense， it doesn't need the exchanges help to get one in two compatible with each other of 5 and 6。

Okay， is that clear？On the other hand。You still would really like them to report Okay。

 so one outcome， which is not the one we want， which is that the first hospital does the surgeries with one and two without telling anybody。

 H 2 does the same thing for 5 and 6， and then they report their leftovers to the exchange。Namely。

 the pairs 3 and 4。 They're not compatible。 So the exchange is not in a position to help if it's only given 3 and 4。

If， on the other hand， the two hospitals resist doing these matches internally。Okay。

And they report all three of the pairs to the exchange。 Then using the vertical edges。

 everybody can be matched okay。So the point is if people try to handle as much internally as possible and their incentives for doing that。

 you want to sort of have as many of your own patients， you know， you want to save their lives。

 You also want to do the surgeries in house because then you sort of make money on the surgeries。

 frankly， So if they try to do as much stuff in house as possible。

 we'd only get foreign pairs taken care of。 if they report everything， we get all six。

So we want at the hospital level， we want hospitals to be incentivized。To report。All pairs。

 including those that they're in a position to match internally。YeahThat's the point of this example。

One of the second example is that this is easier said than done。So， instead of a。Path on 6 nodes。

Suppose we have a path on  seven nodes。So suppose we have truthful reporting。

Meaning that actually the two hospitals really do tell the exchange about all seven of these patient donor pays。

How many of those nodes are going to get matched。6， but I mean， there's 7 nodes。

 You can't match a odd number of nodes。 So one of these7 thatll belong either to H1 or H2。

 you have a choice is more than one max matching。 But any max matching will leave somebody。Unmatched。

Okay。So what So say your're H1。You take a little game theory。Is there anything you're tempted to do。

So what's really tempting is to just not admit the existence of 2 and 3 to the exchange。Right。

So if you're H1 and you hide the existence of2 and 3， you're left with this graph。Okay。

 so one is now an isolated node。And all it's left， other than that is a path with 3 hops，4，5，6，7。

 The unique maxs matching in this graph is to match 4 with 5 and 6 with 7。

And then H1 can surreptitiously， internally match 2 and three。

So that's a way to guarantee that all three of its patients。Get matched。 And again。

 if it reported everything， it could not guarantee that all its patients got matched。Okay。So， H1。

Wants to hide two and three。What about H2？Well，7 is Z under H2's control。But。

So it's 5 and6 is the one you want to hide。Okay。So ultimately。

 you want to sort of force there being a unique max matching on what's left that covers all of your unhidden notes。

So if H2 hides nodes5 and6， that leaves just an isolated node7 and it leaves this three hop path on 1。

2，3，4， the unique max matching of which matches one and2 and4 and3。

 and H2 can just go ahead and surreptitiously handle five and6 internally。So again。

 H2 has an incentive to hide two pairs to ensure that all of its patients are matched。Okay。

So what I've just given you actually is an impossibility result。

 I've actually just shown you that you cannot have surplus maximization in the form of max matching And DS S I。

 C， in the form of hospitals have a dominant strategy to report all of the information in the exchange。

 This shows it cannot be done。Okay。But this， I mean， this is the real world。

 This is really how it works。 You really do have hospitals reporting these things to the exchanges。

 and they do have the ability to hide these pairs， if they want。So， you know。

 you do the best you can。 There's some trade off between surplus maximization and sort of incentive of compatibility on the part of the hospitals。

 and you just try to find a sweet spot where you give up not very much on either one。

 So that's sort of exactly what a lot of the research in this field has been doing over the past couple years。

 at least on the algorithm that game theory saw。够。So any questions before stable matching。

 That's all I got on kidney exchange。How many of you have seen stable matching before。奥库。

That warms my heart。Even so， it's something I can't not teach in an algorithm of Game 3 class。

And it's so fun why would you not do it？All right， so。The setup is you have two sets of nodes。

U and V。Typically called the men and the women respectively， each has the same size。

 Let's say N people each。And everybody's got an opinion。

Each node on one side has a ranked list of everybody on the other side。Okay， who they like better。

So for example。Maybe n equals3。Maybe all of the men agree on the relative ordering。

Of the women preferring D to E to F， whereas the women disagree about the ordering of the men。

 so this would be the inputs。A ranked list for each of the nodes on the other side。

But we all't understand the objects are stable matching。Defined as perfect matchings。

That is a matching in which everybody is matched。And the stability comes from the following property。

So if you look at any pair， which is not matched。Okay， so again。

 the first thing is you have to be perfect matching。 so there are n pairs that are matched。

 Then there are all these pairs that were not matched。For each of them， almost n squared of them。

It should， it should be the case that either。So， either。You。Prefers its mate。The prime。

So that is whoever actually got matched to in this allegedly stable matching V prime。

 It should prefer V prime to V， this person to whom it was not matched。偶尔。V prefers。

It's mate you prime。In the allegedly stable matching to you。

So the reason you'd be in trouble if both of these conditioned failed。

Is that then they would be susceptible to U and V running off together。

They'd both be happier often with their current proposed mates。

So if theres no pair of nodes unmatched， you mutually agree they'd rather run off together than it's called a stable matching。

Good。Doing case studies and stable matching。 I'm not doing it because it would be sort of like shooting fish in a barrel。

 It is kind of like too easy almost too straightforward。

 So the algorithm I'm about to show you the proposal algorithm credited to Gail and Shapley。

 they came up within 62。 It actually turns out exactly the same algorithm unbeknownst to them was invented earlier。

10 years earlier almost。 And since the 50s has been used to assign recent graduates from medical school to the residencies。

 So one side of the graph is the doctors or the residents and the other side of the graph is the hospitals。

 There are other applications as well， not only to labor markets， but also to school choice。

 assigning students to elementary schools。Question。谁。Yeah。

 so you can extend the stability and notion， much like the way we talked about the core of the top trading cycle algorithm。

 where you can ask about large subsets that might want to succeed and do better。

 So you can define the core in that way。 It turns out the elements of the core are exactly the stable matchings。

 So with a setup， it turns out pairwise coalitions。 If you can get them all happy。

 that's a sufficient condition to get everybody happy of any size。😊，Is there something in the back。そ。

Excuse me。Perhaps you know better than I do， Not sure。I'm not the 50s， so。Doctors， school kidss。

Et cetera。I would say the similarities to actual courtship are superficial。So。Here's how it works。

So you have a main loop。 Okay， so initially， nobody's matched。

So as long as there's some man or some node on the left hand side， who's not attached， okay。

Let's call it you。There are many such choices for you， you pick one arbitrarily。So you proposes。

So it's top rank option。Who hasn't already rejected him。In other words。

 each man just works its way steadily down its list， starting from the top。Each woman。

Entertains only。It's best offer。So far。So the woman always accepts the first offer that's deemed to be better than no offer。

And then。Your mileage may vary。Every time you're proposed to a man who is higher in your own preference list than the one you're currently entertaining。

 you break off the old engagement and start a new one。Okay， so over the course of the algorithm。

 from a given woman's perspective， they are engaged to these success， successively higher ranked men。

Oh yeah， where's my example。Here's my example。Good。So。So over here， for example。

 we might begin by picking A。 A likes D dust。Do you accepts， because that's the first offer。

So now A is attached， B and C are unattached。 Maybe we pick B。 B also prefers D。 So B proposes to D。

 D says no， that's worse than an offer I've already got。So that's rejected。

Maybe then we move on to C。 C also tries this luck with D。Again， is rejected。 D prefers A to B to C。

Now maybe return to B， maybe B goes for its second choice E。That's accepted， C tries for E。

Is rejected， and goes to F。And so the stable matching computed by this algorithm in this instance is just the three horizontal one。

过。All right。So the claim is that the claim is threefold。So first of all， the algorithm terminates。

 in fact， in at most n squared iterations。Second of all， when it terminates。

 it terminates with a matching that， first of all， is perfect。And second of all， is stable。Right。

As a consequence， no matter what the preference lists of stable matching always exists。

 a fact which priori is by no means obvious。 So this is a constructive proof of that。So， theorem。

Yet stable matching。Alright， so first of all， let's just figure out that it halts。

So how many proposals could a given man possibly make。

And right it just walks from its list from top to bottom。 Okay， it never goes。

 It never repprooses to someone it's already proposed to。So if it's the most n per man。

 it's the most n squared overall。So how about the perfect matching property。

So has to get a little more interesting now。So suppose not。Okay， so it was not a perfect matching。

Then in particular， theres some man who is unmatched at the end。

Which means it unsuccessfully tried to propose to every single one of the end women。Okay。Now。

 when one of those women rejected him， it's because they either already had a better offer or she received a better offer later。

Okay， so in any case， this man was rejected because of that woman he' was proposing to was engaged。

And remember， with a woman， it's once engaged， always engaged in this algorithm。 Okay。

 you only are engaged to better and better men as the algorithm perceives。So， that would say。ち。So。

 some man。Rejected by all。VnV。So that would apply that all women are matched at the end。

Because once engaged， I was engaged。But if all the women are matched。

 or they can only be matched to the men。 So all the men are matched。

 But the initial assumption was that one was not matched。 So that's a contradiction。Ac claim is。

 in fact， not just a perfect matching， but a stable matching。So why。Consider a pair。

 which is not matched by the Gail Shaey algorithm。How could that be？What going to happen in two ways。

One is that you never bothered to propose to V in the first place。Well。

 you was working its way down its list from top to bottom。 So if it didn't get to V。

 that means it stopped。 I。e。 the algorithm ended somewhere above V。

So U ends the algorithm match to a V prime。 It prefers to V。That's enough to lock。

 That's enough to satisfy the stability property。Well， suppose。Suppose you did propose at some point。

Well then either at that very moment， it was already the case that V was engaged to somebody she likeds better than you。

 or maybe later on in the algorithm， she got an offer from somebody she likes better than you。

 Either way， The reason you proposed to V and you was not matched to V at the end of the algorithm could only be because V got a better offer。

And then， as the algorithm concludes。The quality of the man to whom Vs engaged could only be higher。

 So it's always going to be the case that it's better than you。哎。So that's the Gail Shaplely theorem。

Reposal algorithm terminates quickly and squared iterations。With a stable man。

I mentioned that the algorithm is underdetermined。For example， in the very first iteration。

 every single man is unattached， so you have n choices。Of who you pick。In general iteration。

 there can be many different choices for which unattached man gets your proposed。Now。

 if there were only one stable matching。Then by virtue of always terminating with a stable matching。

 it would be clear that the output of the algorithm was independent of those decisions。However。

 it is not the case that there was always a unique stable matching。

 There wasn't the one example I showed you。But there is not in this one here。

So imagine both sides disagree on who is better on the other side。Ops。Good， good， good， good。Good。

 good， good。So。Because this particular implementation of Gail Shaia。

 I showed you is the male proposing version of it。In this case。

 where the men disagree on who's better， Well， each one is going to propose to its favorite。

And this will be the output。It's a stable matching just because each man gets their favorite choice。

So they're never going to want to elope with anybody else。

Each of the two women get their least favorite choice。I could， of course。

 run it from the right hand side。 I'd get something different。

That would also be a stable matching with the opposite properties for both women。

 get their favorite choice， and both men get their least favorite choice。

So there can be multiple stable matchings。 so now we might be wondering if the Gael Sha algorithm outputs different ones depending on how we run it。

So， let me explain。Why it always outputs exactly the same stable matching， no matter how you run it。

 And they will also give you the clue for why it should be strategy proof for the men。I。e。

 if the preferences are private， they should report truthfully and why should not be strategy proof for the women。

 which are the final two points I want to make in the lecture。So， make that precise。

Fix the men and the women， and their preferences。As we now know。

 there can be multiple stable matchings。 In fact， there can be a lot of different stable matchings。

So for a given man， let's think about his best case scenario。So for you and you。

But the best case scenario for you。Be the top ranked woman。不。Match to you。In some stable matching。该。

So conceptually， I just iterate over every single stable matching。

 You're not gonna to be matched to the same woman in every single one。

 but you'll have one favorite over the whole set of stable matching。 That's B of U。And the theorem。

It's kind of amazing on a few different levels。Is that no matter how you choose the proposer in every iteration。

The output of Gail Shapley。It's not just uniquely defined。

 but it's crisply defined exactly as the B of use。So it matches each。You and capital U。To be of you。

Interview。So， it's simultaneously optimizing。For every single node on the left hand side。 remember。

 B of U says， suppose I don't care about anybody else in V or in U。

 I just make little you as happy as possible。 B of U is as happy as I can make little you， okay。But。

 you know， conceivably， I'm using very different stable matchings to make man number one happy versus man number two happy。

 And this says， no， actually， there's just a single stable matching where from every single left nodes perspective。

 they're as well off as they could be in any stable match。😊，So that's pretty amazing。

As a consequencesent， scaleship was uniquely defined。

This is certainly a suggestive that if you're one of the left hand side nodes。

 given that you're getting your best option in any single stable matching。

 probably you should report truthfully。 And that's a true fact， but it's not trivial。 Actually。

 I'm going to put that on problems at 3。 I' going to take some work。Okay。Secondly。

 it should be intuitive。 and this is easy enough。 Ill put on the exercise set that if you're on a right hand side node。

 it turns out an analog of this theorem is that you're getting your least favorite option in any stable matching。

As you might expect， it's not strategy proof。To input your true preferences if you're right hand side note。

Okay， so those are the key incentive compatibility properties of the Gail Sha algorithm。

 strategy proof on the left， not on the right。So I'll see you next week for selfish routing and the price of energy。

