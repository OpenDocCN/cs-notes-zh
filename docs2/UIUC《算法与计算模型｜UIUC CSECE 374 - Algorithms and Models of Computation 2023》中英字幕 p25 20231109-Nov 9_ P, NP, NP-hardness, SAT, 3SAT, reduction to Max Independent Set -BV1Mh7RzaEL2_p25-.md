# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p25 20231109-Nov 9_ P, NP, NP-hardness, SAT, 3SAT, reduction to Max Independent Set -BV1Mh7RzaEL2_p25-

![](img/4d7edc7543ce05cd0987e1dac29d85bc_0.png)

这里。啊，就这样。但是个不车后。

![](img/4d7edc7543ce05cd0987e1dac29d85bc_2.png)

系い。嗯，我这边这个。对。う。Okay。Thanks for having for gra cold Frank Grba to regular fall weather。

So the term solutions are out。And as happens inevitably because professors are human。

 there were a few minor errors in the exam， one thing right off the bat。

 if you remember problem one B， everybody just got full credit for that because there were errors in the answer little bit。

If you looked at。The red literally， which is the only way to read math。

He read the recurrences in the way they were written， both recurrences actually infinitely。

So the correct answer to 1B for the versions of the recurrences that you got in your rancho the cliff was no。

The correct answer for what is the best thing to memorize this in the evaluation time is no。

So everybody just got full credit for that。嗯。On。Problem two。

The initial version of the solution that I posted ignored the edge weights because the previous。

Some of you may have recognized this problem as being in the fodder。

 but being about Rachel instead of Chandler。But Rachel that removed it's also so I had to add Fsa but in that version of the problem there were no edge weights so I put on the edge weights that I forgot that I put on the edge weights so if you've ignored the edge weights there penalty so if you answered the question correctly as if there are no edge weights fine full credit if you answered the question correctly as though there are weights great full credit。

So don nobody gets penalized for the mistake that I made。And then last one。

 this u this abetic sequence stuff in the version of。The solutions that I posted initially。

 this computation of this step sized delta was incorrect because I implicitly assumed that the array was sorted in increasing order。

 so if you assume the array is sorted in increasing order without saying anything。

 or if your deelta is only correct when the array is sorted in increasing order，Fine。

 you get credit for that so if you make the same mistake I did， we will not penalize you。U。

Neither of these in my mind qualifies as a significant enough error to pull the trigger on the question entirely because in both cases。

 this would have been， you know， in the order of one or two points out of 10。

And for any perspective in order for me to， the key one is significant to me means at least four or five points。

So。Generally speaking on exams， we try to grade leniently。

So significant really needs to be significant and especially because these things are worth so much more points significant really needs to be significant for you to invoke that everybody full credit clause。

The way I did for1 B， the recurrence infinite looping。

Significant everybody gets credit at the end and everybody on the conflict exam， by the way。

 also got full credit for this。Even though those recurrences were correct。Okay。嗯。I'm happy to answer。

Other questions about this， but since this did come up。

There was some quite a bit of back and forth between students and core staff on Discord about this。



![](img/4d7edc7543ce05cd0987e1dac29d85bc_4.png)

I figured I had needed to make my。

![](img/4d7edc7543ce05cd0987e1dac29d85bc_6.png)

My stance completely clear。Any questions？Yes。哦，我记得来。Okay。So just said double check after after。不。

So last time。We。T starting talking get out reductionives， becoming different kinds of problems。

Mostly involved are in exclusively involved different kinds of problems。

I want to give a bit more of the backstory of why we're doing this and start branching out into problems that are not exclusively about graphs。

😔，Or not in the in the sense that we've been dealing with before。 So those of you who。

A you CE majors。Probably recognize these these the top three things。

 those are an an gates and orgate and knot gate， these are the basic that。Comp componentss。

Of every piece of visual electronics， the idea is that the wires coming in in each of these gates。

Have different voltage levels。If the voltage level is high， for example。

 maybe that will represent the boolean value true and if the voltage level is low。

 that will represent the boolean value false。And then inside these little geometric shapes。

 there's a collection of diodes and transistors and other circuitty thingss。

That enforces a relationship between the voltages on the incoming wires and the voltages on the outgoing wires。

So the orgate， if both。Or at least one of those two wires and high voltage does the output wire is carrying a id voltage。

 it's true if both are carrying the low voltage coming in， then you get a low voltage coming out。

So acts like an or date if one of the incoming wires represents true or both。

 the output will represent true the end date。The output will represent true if and only if both of the incoming wires represent true and the notet just inverts so if true comes in。

 false goes out in the vice versa。And this is a universal vocabulary for building in circuits that can compute any function from any collection of this。

To another collection of bits， so here down below is a small prototypical example of a boolean circuit that has five inputs x1 through x5。

And information flows through the survey from left to right。Yes， it's a dad。

 otherwise you get more interesting in behavior that we don't want to talk about and some bulloleing that comes out on the right。

So。Really what you should imagine。Is。There is a light bulb here。

That turns on if the output value of the circuit is true and you've got little switches。Here。

That could be set to either on or off。And。But I give you the description of the circuit as a directed acyclic graph。

That in this case the edges are all directed from right to left you have to be a little bit careful about what to do in nodes like this those aren't gates those are just splits so we'll just let them be additional atices so I have some vertices that are just split split the signal。

I have some bird des that are gates and those are labeled and or not。

And I about one node that representss the output and say M node the represents the input。

I could evaluate this circuit by doing a traversing the dag in topological order。

So this would take me。You know， time that's proportional to the number of vertices and edges。

 which is really proportional to the number of digs and ws。嗯。

So this is really immediate way to be represented。Moving functions。It's in every single。

Digital device。That you've ever seen。It's a little eye clicker thing。This Apple pencil。

 the USB cables connecting my various devices here， microphones。Every you one as well。Now。

 the Russians in the 1950s when they were thinking about Peboard again， were asking the question。

 how hard is it to solve the satisfiability problem？ch is given。A boion。Circuit。Okay。Can we turn on？

The light。I give you a complete description of this circuit， say， as a graph。With labeled nodes。

 and I want to know if there is case setting of the switches on the left。

So that the light bulb turns on。On the right。So if you're lucky enough， the light bulb will。Tur on。

 okay。Now， if the circuit was inside of that box， initially the briefly say。

 and all you see is a box that is put from the front and a leg on the top。

 there is little nothing you can do that's better than trying all two to the un possible settings of the switches。

And the reason for that is the comp the black box， when you announce I' done。

 I've only looked at the I don2 n minus side of the phoide those switches。

The guy holding the box says， oh my God， it's a Yeti and you turn around and look he swapwas out the box for a different one。

Where the light turns on， you' can only give you set sta， which is to some about product。

Now you distract， but try there are all ones I I did before again， you want notice a difference。

As far as you know， the new black box that the adversaries put in front of you was always there。

You've no way of distinguishing between the original box and the new box based on the tests youve actually did your answer。

But now I mentioned wrong。So that proves that in this black box model。

 you cannot do better than trying every possibility， but now the question is， I did you ever do that。

系啲招。The plans， the boxes that made out of plastic， you can see through， you can pull the parts out。

You can play around with it， write a code， do whatever you like。And still， as far as we know。

The best that you can do to decide whether the light bulb can come on is to try either physically or in simulation or by working out on paper every possible setting of the input switches。

系。Now， the fact that。嗯。You can verify。That a setting of switches would turn on the light by running through the circuit en topological order。

Means this is solvable in polynomial time on a non deterministic machine。Now if you remember。

The difference between the termus and I A is nomin least P。The deterministic pilot state machine。

 when you were in a particular state， you were single。

 there is exactly one new state that the transition that of the machine will come in。

The evolution of this being is completely determined by nucleus and the transition function。

In a non deterministic finite stake machine， you may have multiple changes at the same label leaving the same state。

And one model for how you should think about non termminism is。When you're facing with that choice。

 the universe branches and for each choice you're an comparable universe where you take that choice。

When you either run out of options。Or you reach the end of the input and you're not in an accepting state。

 you say oh well and you destroy the universeus。So only universes in which you make the right choice。

That every possible step needed to do the second state survive。So in this case。

 what my nondeterministic machine is going to do is its going to try both options for x1。

 both options for x2， both options for x3， and so on to both options down to XN。

 branching me to tune in the N in parallelial universe。😔，With these as parallel universe， I will。

Figure out by Tracy the concerneding an Mo long order whether itll help and son。

 if I find myself in a universe where a that is dark， I more years。

As long as they're into one  mu with a that will comes on at a perfect victory。

That means this formula is satisfied。In every universe is destroyed。

then there's no setting where the level comes on， that means the circuit is not satisfiable so this is what I mean when I say you can solve the problem of the diploma this time using a nondeministic con you make nondetermintistic guess。

The right options to input the input signalss。And then you verify mind you have the right of choice。

嗯，因 what就是。So saying this a bit more generally， this is equivalent to saying。We can verify。A yes。

Answer。In。Polynomial time。诶。😊，So if I say， yeah， set the switches to these and then you set the switches to those and lo and behold。

 the light bulb comes on， I have convinced you。It theres no eternal。

I can't necessarily convince you of that fact critical， but if I is away from the world level well。

 I can convince you of that by just telling how to set experience。诶。So a problem that。Has this。

Characteristic where I may not be able to solve at from scratch polynomial time。

 but it's possible to convince me in polynomial time that the answer is yes。

This is a problem in the class NP。Non deterministic。Polynomial time。Now。

 the class P is exactly the same。Except for the non。诶y。😊。

Does this setting of the circuit turn on the light bulb。

 that's something you don't need the power of non determinism to figure out you just traced the circuit here is light is it sorted。

😡，Here is a graph， does it have five so components。

Here are two screens evidence is letter up and names。

These things that we've been working on for us it's not we developed a polynomial of my algorithm。

 all of those algorithms were deter， you never guessed and hoped that would the university North went out stroke。

嗯。So。The question that in modern terms。Or that these pet artists were looking at in roughly 50s。Is。

Are these new classes of problems to state？If I have a problem。

Where I can be convinced that the answer is yes。Does that problem necessarily allow figuring out the solution of those scratch？

If I' haven it， if I have a homework problem。And I can read and verify the solutions in only an hour。

Does that mean I should have been able to solve the problem from scratch in owning an out？Yeah嗯。

Are there plans where we can。Whereerify yes and number of time。

 but also verify no number of time empty becomp。Okay， so we haven't talked about N completeness yet。

 but I do want to point out that you're noticing here there's asymmetry in the definition of M which says I can verify yes answers you call in real time it's not saying anything to all about how quickly I can verify evidence。

There's another impossible coding team to suspect to the office。

 I can verify no answers publicly put not guest answers。Well。

 I'll draw the Mc mouse diagram of what we thinking， how we believe these sets intersect。

So there's a set P of problems that we can solve deterministically from scratch and polynomial time。

 there's this set NP。That these are questions where if the answer is yes。

 there's a proof that you can walk through and verify in polynomial time。

 and there's the symmetric class coNP where if the answer is no。

 then there's a proof that you can verify in polynomial time that the answer is no。

And there are problems that sit both in P and in NP， sorry， both in NP and in Co andP。

 so you can verify yes answers。And you can verify no answers。

But that doesn't imply that they can be solved from scratch。Yeah。

This is the picture of like se illusions that we believe。

But there are other branches of the multiverse that are possible that have different inclusion relationships here。

Give a free sta problem。对。ir we haven't talked about threeat yet。

 so we'll get there we already talked about it。We talk about S。啊。

So given the staff problem given a staff problem where。Where wires cannot branch it。听到。

Branch out words。But meaning the farm is a tree。诶。He to be solved in poly at the time。

So the question is， if I know in advance that the circuit is a tree and not a more general bad。

And it's not a black box you can see it Yeah， I'm assuming whenever we're talking about Sap we're give the just complete description of the circuit yeah。

 I'm pretty sure when when if you happen to know that the circuit is a tree so the output of one gate only goes to the input of one gate。

It doesn't branch then there is an near time algorithm， but most circuits are not trees。

 so the fact that the special case is easy to solve doesn't say anything about the more general case yeah。

Okay， so non deterministic means at various points in the execution of the algorithm。

 either a choice， I can either say， well， I don't know whether this variable should be that true or false。

So one parallel university set trying put one parallel university set false。

And in those parallel universes， I discovered either one that I made the loan choice that I blow up and use and feel what asking me me。

啊。So the black box would only like inub the black boxly to the black box created in soil。

We lots of made glass， that's the world of the actually。

That's the only case to S meet or give the service to you the complete information。

That's the work we're talking。Yes。😊，So he is the problem that here problem is against after nose and you walk through your right code and it solves it in every time。

没有 yes。Yeah， to the。Its great。好意啊。Yeah， so this is been also an important point to notice that there's a gap here that has three inputs。

 so in my definition the circuits that， I'm allowing the gate to have our and gate to have a many too。

I do replace a single an gate that has paid inputs。

With a tree it came minus one in into which has two inputs。

But that wouldn't blow up the number of why that only blows up a number of wires by a factor two。

 so it doesn't really affect how good means solve all。Yeah。法。Okay。

 so I tell you that the answer is yes， and moreover， I was prove you， here's the privilege。

You need to breed the flu。And agree with that it is approved。经你好问。

So if I give you all of the guesses that I made in an othistic algorithm， so were saying this。

 you can trace turn the algorithm now they're not vector。

 deter thing do about algorithm and you can see of the algorithms in。

Oh so like that would be basically their money。So a satAT bubble is the more general problem of here's the circuitt and you come to the left。

The verification output is here in Conia and here in the is which。第十个话告。我。喂喂打你。

Can you say that sense again obviously in the？So， what is the American。我的是是。

Takes the form iter and variables。And thank you。Yes， so the verification algorithm， for example。

 would say， let's say x1 is true， x2 is false， x3 is true， x4 was true and x5 is false。

Then that means the output of that first and gate in top left the screw and the output of that knot gate on the bottom left the false and walking through the graph。

So if you give you another example， a problem in M？

Hero is a graph doesn't have an independent dissatisfi。

The only thing when you're not how to do is try all sons exercise 28。That takes a really long time。

 but if I color in the 28 person you can say， look， I believe this isn understand。

 then you only't have to stand when and linear time for draft and verify it to know that my purpose。

If I say here is of graph， Id think it contain it doesn't contain an Hamilton cycle and these in the only thing I know are is trial of verses that this saw done throughs estimate from many of those。

 but here the graph and here was type many of the have one new cycle in this graph。

Then all of time you can be verify， yes， every as discipleism measuring the draft but yes is a cycle is a emergency in draft and after a lean and work say yes convinced the this draft。

So the role of our whole this complexity we actually care about is just what's the answer to this question？

The fact it's NT means that when the answer is yes。

 I can give you a certificate proof that the answer is yes， it is easy to check quickly。

so whenever it spend a about time， I see。he means announced。

And so formally door time here means set on the machine， but on the other hand。

 Python interpreter was just as well because Is simulateulated the Python interpreter on machine all。

So it doesn't doesn't matter what systemed and machine model we're using。Normallyally， yes。

 encourage。you transition step take Yeah， each transition step in the term which you can take by definition。

One time。One step。But if you think of it as。I write a Python program that I wanted to run and call it omeal time。

 that's completely fine。嗯。Now。So the big question here is， is p equal to NP？嗯。This。Is。

One of the $1 million opening problems that the Clay Ma Institute posed at the Turnable La。

We got7 questions。There was a remon I thought just did a concrete。

 there there was some physics stuff about Navier Stokes equations， one of them has been solved。

Theor Carol put the last link in the chain to solve the Po projectjecture。

 he refused his million dollar prize。Because he saw other people trying to take advantage of him and claim more pressure than they saw whole this whole visit corrupt I knowing lived with my mom。

 I basically in mob cow and playing ping pong all day。No， I'm not exaggerated。

So this problem is still flood out there， it's been first formally moved in the 1970s by Steve Cook。

There's a particular theorem by Steve Cook and La at Levin。

 Levin was one of the people in the Paraor school， it's the so called Cook Levin Theorem。

It says if satAT can be solved in polynomial time。😡，Then he is equal to NP。

So if there is a polyable time algorithm to evaluate the balloon circuit and say， yeah。

 I can earn light bulb that we can come it or no， I can't earn light bulb。

Then there is a multiple time algorithm for every problem。

That the only requirements is who can verify us poly duty time， for example。

 they would be being called on your out to defining the largest community have。

West than the graph smallest perfect there would be a poll time algorithm to decide whether a graph contains an cycle。

 there would be a poll wheel time algorithm to find this short Hamiltonian cycle travel Hamilton。

There all will find out you to decide how unique colors you need to a for the graph so that every ad colors on it。

 which means among other things， there would be a poly a meal time algorithm to do optimal register allocation with they compile。

There would be a polynomial time algorithm for ridinging package lands up on your house。

 there would be a polynomial9 algorithm or ridinging gas drivers to drive neighbor that left。

 thered be a polynomial time algorithm for knowing when to collect viewide bicycle signalss spring down。

 but still can mineral amount gas。There'd be a polynomial plan algorithm for you know。

 creating curencies， it'd be a polynomial time algorithm for thousands。

And thousands of other questions， which if you formalize it down to yes their questions。

And this the the answer yes。We don't know the answer to this question。

And despite at more than 50 years of continuous work。

 we have no clue how to even approach answering this question。

And I say that in this sense there are natural approaches to。那找了一个他是。For example。

 maybe every problem in NP can be formulated side of the programming problem metaized into the polynomial side of data structure。

 maybe every entity problem we formalized as a linear programming problem。

 that with a polynomial number constraints in polynomials under conventions for every one of these natural aruptions that people would propose。

 we can prove that it doesn't work。We can not so not only we have no we have no idea how to prove the the。

We can prove that we have no idea how to prove。我。We are incredibly this weirdly frustrating state of ignorance。

On the other hand， as a wall of physics。Is it easier if you solve problems with crack or is it you need to detect other people's solutions？

Obviously， it's easier to let somebody else do the work。Otherwise。

 no would be go to Staholders flow to solve their homework problems。Um。

 so it's sort of the Richard Feynman， when he first saw this problem was like。

 what there's nothing to prove。Of course， it's obvious if I already have a proof of the answer。

 of course it's easier to check that and come up with the proof from the beginning end。

And so that's actually the attitude that most algorithm designers have is for purposes in design operation depending about what your。

 the answer to this question is no。As a physical law， it's lots of evidence to support it。

 not a mathematical group but evidence and if someday somebody comes along and proves this wrong。

 well， we'll do exactly what we did when people showed that the Gcent model or universal wrong will pass。

And people mechanics didn work because we have relative we'll adjust and people started talking about quantum mechanics instead of things having absolute positions and velocities。

 these weird amplitudes and。And spooky action at the distance， okay， we'll adjust。But until then。

 we're going to run with the best model we have。Yes。So what do you mean？

So the the question not how we want to come them that there is coming here。啊。

You conclude prove that the number of movess that you need is exponential in。

So that means you writing the down already it takes me long。

 it takes me long to read that entire entire book。You the time project verify the group needs to be polyial in decide side of neighbor one。

The our really problem doesn on the other hand。The fact that you write the algorithm there the sunset means I've already solved the problem。

 so you say， if you give an end is there a solution no problem or yes。

Given zipping of the dip on hours of cow call， is there a solution he asked？关系啦。

So as at the same question。嗯。It power is not leadership。系。

It's complicated only because the solution is law。Yeah so how do we that's independent so the question is。

 what if this is like the continuum of my art depends on what model of sector you're working in？

People generally don't believe that that's true by APOB。I be weird。

 my running time the running time of this piece of Python code of beer depends on which bottle of Cella Frank are said happy to use it。

No， it doesn't because I run the algorithm。very strains in that。嗯。So what I want to point out。

 first of all， is the way that we use the Cook Levin theorem。Is we say， okay。

SAT is a really weird sort of。Each to a problem if we could solve this problem quickly， we be done。

 the whole House of cards would fall down。So I'm going to define what it means for a problem to be NP hard。

So x is NP hard means there is a polynomunal time。Proedduction。

In the sense that we looked at on Tuesday。From sat。To x。Not from S to sad。

So what this means is that we're going do when I say that the antonia cycle problem is in hard。

 what that means is I can write an algorithm to solve the sas。In autumn time。

If you can write me an algorithm， this's all me cycle economy。So to say if let's hypothesiss。

 suppose， and how we detect the problem with these all quickly。Then SAP can be solved quickly。

 but we don't believe SAT can be solved quickly， so we don't only have a living site。

It's essentially an argument by contradiction。Yeah。Why so。If act is a more difficult problem。

 then why are we reducing？然ally。That difficult to a more difficult check on the fire extinguisher like the matched throat on the test。

 that's the way reductions work we always reduce from the easier problem to the harder problem。

Because that's where all the harder problem is what's encapsulating all the real work。

 all the real work in the charity health problem is in competing that strongly connected components graph。

Like how is it reducing something that's the word that we use in English to describe solving one problem using the black box subrtine for another problem。

You've already solve this， so I can reduce my problem to yours。Once your problem is solved。

 its solved。It is a partner。可以。Okay， so I want to show like a couple of examples of NP hard problems。

 the first one I want to show is threeSs。So freesat is a particular version of the satisfiability problem where instead of a circuit or an equivalent farming lot。

 I give the ruling formula me to do a very， very， very subtle。This form along the bottom。Cers。

So I'm given。A Boolivan。Formula。In conjunctionjunctive。Normal form。With。Three literals。嗯。Pause。Okay。

 what is conjunctive normal formal？Well， okay， so you'll notice this formula is made up of these parenthesized expressions。

That are all added together。Those parenthesized subexpressions， these are called clauses。

Each clause is three things work together。And each of those things that are worked together is called a literal。

A literal is either a variable or the motivation of a variable。😡，So here the literal Z20。

 that's just the variable Z20， here the literal bar， that's the complement， the negation of Z20。

 so a conjunctive normal form means it's an and of or's of literals。

Another way of saying this is that I have an and， you know。

 my circuit looks like an and thing with an or， the ore has degree3 and some of these have knots in front of them。

Okay， so this is any number。This is always three。嗯。So this is a very special type of formula。

 it turns out not terribly difficult to date an arbitrary。

Crcuit and transform it into the removalative formula in this very， very spectral form。

 started by ping gates with large inputs and transforming it binary gates and then writing down clauses or gate。

 and then while some of those clause would be A equal B or C everything like that into ands and orders。

But that whole transformation takes， it turns out linear time with a not insignificant concept。

 but's still linear time。So that formula that's on the screen right now is a three sat encoding of that circuit。

U。And when you do this transformation mechanical living， the original circuit is satisfiable。

 meaning I can turn the light bulb on and again， if and only if this formula is satisfiable。

 meaning I can plug in values for the variables and the thing will come out to be true。系。

So I don't want to go too far into this。😔，But morally。

 it means that I can just write a free year and we're going to start。

Our chain of reductions from three set yeah。嗯。Let's go down。好，这这点哎。So。Um。

I'm going to look at a particular here's a variable。Right， so this could be either true or false。

So x or x bar， either one of these symbols， these are literals。And I just write it like this。

 I don't want to。Do you use the or as a thing？Yes， if it were in a。3 little。

And it together and then it would be a different problem when I don't want to talk about the different problem because you ask me to slow down。

I want to slow down and want to go through the definition more carefully。

 but I need to talk about the thing I'm defining and not something。对。So。Literal。Or literal。

Or literal。This is a cloth。And then claw。And Cla。And。And Clas。That's not an A that's a little wedge。

This is a three set。Formula。嗯。😊，So I might get something that looks like A or B or C bar。And。

B or D or E and。B bar or C bar or E bar and。That's an example of the input to three7。

The question that three side is asking is。A is that A can be true or false and can I set B to be true or false。

 and that set C to be true or false， and can I set D to be true or false and so on for all the variables。

So that this formula evaluates to true。So for example， if I set a equal to true。And。

Let me make this a little bit more interesting to set B equal to false。And I said C equal to true。

And its that D equal to false。This clause now becomes true or false or false， which is true。

This clause becomes false or true or it doesn't really matter because I' already got true or something so that second clause is true。

 so let me go ahead and set E equal to false。So this is。啊。A is true B as false far as salt。

 so this is true。Be as false， Eva is true， E is false and it is true。嗯。B bar is true， C bar is false。

 E bar is true so that third clause is true， I now have true and true and true and。在那个售活伴里出。A。

So another way of defining little of presat。Is saying is。Given a formula。

 it's called also called3 CNNF three conjunctive normal form。

 conjunctive normal form with three literal strip clause。Can we assign？Values。To the variables。

So that。Each。Cause。Has。At least one true literal。可以。😊，So， right？He you over be your CP？Here the R。

Ebar was Ebar， could you go with letters and want to respond to you were also so then each group was three。

 one of those time。Now this is a really abstract problem。

And the most natural thing in the world for you to be doing is to try to think about how to solve this problem。

 do not do that。Don't try to solve freet the whole point of showing you free fat is to show you this canonical example of the problem that meinities can being solved quickly。

So if you're thinking about how would I solve this problem。

 then that that's not how we should make it， theres weird this our problems important to understand the definition of the problem。

Now I'm try to solve it。都月太。人高那的。系。Yes。But so this is being economic if problem。

The way that you show other problems isn't hard is use the other problems to try and solve this。

But we can't solve this， but that positive we can't solve the other。好。The other way around。

 we're trying to use black boxess or other problems to solve risk。We succeed see in saying。

 I've about1 an hours of magnitude me cycle， that implies that probably1 hours sad something went on the way。

And what not raise is the assumption I apologize time algorithm。嗯。

So this is the sort of reference problem that we're going to be， you know。

 ultimately everything is going to reduce from。And I think this will be maybe a little bit more。

Hopefully this will be a little bit clearer when I might walk through an example of such a reduction。

😔，Well we going to have time at anyone。But I do want to make it ensure that people understand definition of the problem。

There are pretty questions about what are the problems and what's with that mean。O。So。This。

Is a sketch of a reduction？From three sets。To the mask set。

TheSa national is that problem that we solve。意是。Okay， so。

The rules of the gate are were trying to reduce release that to mass independent independent Sa eventually what this what this transformation is going to give me is a running time。

Inequality that looks like this。A3atAT on a formula of size N， that's going to be at most。

The time for Max independent set on a formula on a graph size order n plus you know some small thing like this。

If I could solve maximum independence quickly。Then the inequality implies that could solve threecent quickly。

But I can write this inequality in a different way。That's T of max independent set。Is at least。

T of three sat。Minus order n。In other words， maximum dependent set is harder than three set。

So the reduction is actually showing。Not depend is at least hard has to be sad。And there'我。In there。

The way you do that is by designing an algorithm。Given an arbitrary3 CF Boolean formula。

Here's an example right here， four buzzes， four variables I to construct a graph。

With the property that。The formula is satisifiable。

 if and only the graph that I construct has and been sat the per the。嗯。

So I could then take that graph， ask hey， what's the largest that had inside in this graph and it gives me an answer at and I actually to the right size and the instrument have I go hey。

 that means perform a little satisfiable third death and it doesn't give me away answer I say。

 oh that means formula me a almost satisfiable I just heard death and this solve the there that problem。

Using this magic box for maximum independent set as a summer team。

So it looks like I've derived the fast algorithm for three sat， which is impossible。

 so I must have gone wrong somewhere and where I went wrong was assuming that that magic box in the middle。

😔，Exists。Yeah。So we're designing out and assuming that a vast would exit pivot。

And we derive some of these that we figures our involved。就电下得诶有知杀。哎。Again。

 I will step into the details。It will step up the proof carefully， but before I do that。

 I need to make sure that people have at least some comfort level with the outline of the argument。

Yeah。在。是吧啊。That。Yeah。Yes。😊，It's ultimately approved by confidence。

I claim in the back of the those group is possession are， suppose mom， suppose there were poll。

 well then from that logically conclude the three sides of poll。

That means I have over a million dollars， I don't have a million dollars。

 so my assumption needs to win。对。So。I might been5 years ago。

How know that our answer is correct given that think we're buildingling off。

 but we don't know what the next doing。Okay， so problem that's been the set is well defined or any graph that is a well defined answer to the well。

The thing I'm assuming is that there was a polynomial high power picture that。I don't know if or not。

 so the food is a the。这个方式上应关考。Yes。Yeah。好 right。他这发那个发点。而在判。Yes。

 so that red box over here on the left， this is transformed and it turns out the near time。

 that's the core of the polynomial time reduction。I need to know that give a Republican formula。

In time polynomial in the length of that formula， I can produce a graph who size polynomial and length that one。

And the lot lot。对啊对。啊，对别是第3。It turns out that twoS can be solve in poll youll find using strong vector components。

The three S hand so there's definitely a much moregen pattern。

 which I don't think people really understand that it's sort of a something that fall down the and like it's problem for a while to is E for as hard。

So there are problems where you need to kind set of numbers be' split it up and set three lot of the same sum that the Greek auditing bubble that can be hard。

 I have set of numbers I'm just split it out into the pairs that all have the same sum as the artificialing bubble that can be done。

So there's something weird about going through this quickly or to fall back to something that was briefly mentioned a month ago when you spoke from rat and Igrass。

That make these problems become harder。第二。So it might be a little easier if I write the no in needs to ago so you can see what what。

How the reduction works。So un'mso。Resat given some Boolean formula fee as input。Okay。

 so step step one。Is I'm going to count how many clauses。There are in key。系。Then I'm going to build。

Using some algorithm， I'll just call transform for now， I'm just going to build some graph。

And then I'm going to ask。If the size of the maximum independent set。In G。Is equal to k。

 I'm going to return。True。Otherwise， I'm going to return。Boss。

So that little thing that's going over on the upper right over there， that's just a， you know。

 are these two numbers equal？The number of clauses in my original formula and the output of the maximum independent sector。

Oracle。Okay。😊，And I can with the algorithms transform form。And I admit you。That is correct。

So let's start down that road。I'm going to need to add another page here。Okay。

 so here's the transformation over them。Okay， so G has。3K vertices。Reer class。One per literal。

So let me write this down so if I if I start with。A or B or C and I。That's ands and wars。

 always get those mixed up。A or B or C and。B anV or Cbar or V bar I'll write the others later so given given this formula。

What I'm going to。I it's a different color。Given this formula I'm going to write。

 I'm going to have over here a clause gadget。That consists of three。Vertices labeled A B and C。

For that first clause and then down here I'm going to have another clause gadget。

Where the veres are labeled B and C bar and D bar after the literals in that second clause let me go ahead and。

Just point out what's going on here so。嗯。For each clause。A or B or C， I'm going to have a gadget。

 ABC， like that。Here's a clause B or C bar or D bar， here is the gadget， B or C bar or D bar。

Here's a clause， here's the gadget， here's the clause， here's the gadget。

So for each clause in my formula， the first thing I going to do is going to create three verses of threes。

To create this little vertex gadget。嗯。啊。These are。Look text。Gadgets or sorry。

 these are clause gadgets that the。They're gadgets that represent bits of the graph that represent clauses。

Okay， so looks like。This。The second thing that I need is a gadget that representss。

And agree they're variable。That somehow enforces the semantics of these symbols representing。

Consistent。Lo values。So I can't， if I'm going to imagine each of these nodes represents a literal。

 but these need to be defined as true or false consistently。

Then the node labeled C and the node labeled C has to have different values associated with them。

They represent compliments， neations of each other。All， so I'm also going to have。

These these other edges。That connect。NotPs of nodes that contradict each other whose labels obligations of each other。

系。So I' going to move。This down here it's a little of a room。

So those are the clause gadgets and then I'm also going to have edges。Between。Contraicting。Vertices。

She wouldn't really think of these collections of edges as variable gadgets。Right。

 so if I've got an x here， I've got an x bar there， I'm going to have。

An edge connected to them so if I look back at my example here these are exactly the edges that are indicated in red so here I have an edge from a to a bar here another a to a bar here's a D going to two copies of D bar here's a here's a C connecting to C bar here's a B connecting to B bar。

So every pair of literal every pair of nodes where the labels correspond to contradict predicting littles。

 litals， one of which has to be truly other false。I'm going to put down an edge。

That's the end of the description of how the transformation works。Every claws at the triangle。

For every pair of contradictory literals， I have an admit。

Is it clear that I can do this transformation and execute this transformation political them problem？

对。Okay。对。我为睇意。Pro book for me。There are also edges you know their December different variables there because those edges probably。

So the black edges in the figure are edges that we want to cause patternss。

 but red edge is in figure by the edges of the below the very patternss。There are two kindss of ends。

 I mean in the end， it's just the graph。So when I passed this graph to my independent the independent at or to know one kind best to see that。

But the construction ended on fewer concept， yes。Yeah，法庭。对。第告。呃 sorry。Okay even。Yeah。

 what about the end。So the transformation is only done so at the level of the syntax and and wars。

Think of the flaw as as the units in the formula。And that you a pause correspond to triangle in the graph。

And then I mean something that enforce the semantics of variables have values to were false same pay variables to value。

So for variable when we're time as different knows with that variable and knows with that variable date。

呃，你好。This is the complete description of the reduction， I still have to convince that it works。

 it shouldn't be obvious at the point that it works。But it's not going to be wait。

 there's nothing corresponding to that that symbol。I need to need to argue。嗯。And unfortunately。

 I need to do it quickly， so I'm going to describe the sketch。

And hopefully the sketch will be helpful。But complete details may have to wait until Tuesday。

And so I'm going to move this。And I'm going to move。Yes。There just to make myself some room。Okay。

 so the claim。Now is。This formula is satisfiable。If and only if。He has an independent set。Of。Size。

Okay。This is the thing that I need to prove。Okay， now one thing that should be clear immediately。

 I cannot have an independent set a size greater than that。

There are K of these triangles floating around in this after。

 so if I have an independent set the size larger than the K。

 one of these triangles would contain more than one perex in of the。

But that's impossible because at the other7 nothing is connected if I've got more than more me with those triangles is that that feacy is connected。

So the pick principle immediately tells me this graph cannot have an independent set of size more than k。

The only question is whether the largest independent set size exactly a or whether it's forced to be less。

系。That's why this claim is sufficient。So let's go one way here。Suppose。She is satisifiable。

Fix a satisfying assignment， meaning fix values of the variables。

Such that each clause has at least one true literal。Okay。

 I know I can do this because be isatiisfiable。Pick。1。True literal。In each clause。

And then the idea is the corresponding。Vertices。In G are independent。All。

 so let's look at the example again。Here is my formula now this formula turns out to be satisfiable。

 I could set a to be true and B to be false and C to be true and D to be false。If I do that。

 then I can pick out well in this clause I can pick out the literal A in this next clause I can pick out the literal D bar and the third clause I can pick out the lit C in the last clause I can pick out the literal A。

 so every literal has every clause has at least one literal that's true。

Now I've already marked the corresponding vertices in the graph。

And I claim that these are independent， each little comes from a different clause。

 so each of those verttices comes from a different clause guidance then of black end is going。

And the literals all have consistent truth values because I derived them from an assignment of their values to the vertices。

 so there are no managers between the and birth even。但是那是ごく。Yes。系都识。

This D bar is colorful but there's also the other Dbar， I said pick one lit class。

If I picked more than one liberal court clause， I wouldn't get an independent set anymore。

 but I could have picked D bar in this fourth clause instead of a。

 in fact I could pick B bar in this fourth clause instead of A and I would get a different independent set。

嗯，哎，关注。Right。So the other half of the proof， and then will' be done。Is。Suppose。

G has an independent set。Of size。Okay， from that， we can derive。An assignment。To the variables。

That make。The literals。In this S。True。Now I can do this because I know that the S has said dependented。

 I know that any two knows in that asset code。They don't have a raage doing so the red would mean I couldn't consistently set truth values。

 but I can set truth values because there's no redage that forbids it。Okay。

 so I could go the other direction， I could say， okay， here's my independent set， step A to be true。

 set C to be true， set B to be false， I don't care what it is。哎。嗯。

Then because each node in this independent set belongs to a different clause。Then， each。Cluse gadget。

Has。One node in S， so each。Cause。In fee。Has。At least one true。Literal。

And that means that the formula fee is satisfiable。

Building this graph from the formula literally involves just reading the formula whenever I simple。

 I pp down a vertex， whenever I be applause， I plop down free edits。

 and then later I check consistency for every A I make an edge to every A bar。

 this whole thing could be done quite a root for and I know every few times。啊，各种原所员的然。啊，泡人。

So if I had a magic algorithm， huge maximum of independent sets in polynomial time。

I could use it this way to derive a fast for that， you a formula。

 turn it into a around after the ones been been the ground。

 check to see about people who around with clauses。

The only part of this process that has any possibility of being slow is finding the maximum independent set size and since we know there's no mass problem for freesat。

 that part but actually be slow。So this is the proof that Maxim Independ said is empty hard。

We'll see more examples。This is。Not an easy thing to grasp。

But we'll go through it again and again and again until it becomes a bit more familiar。Thanks。

 everybody。No。

![](img/4d7edc7543ce05cd0987e1dac29d85bc_8.png)