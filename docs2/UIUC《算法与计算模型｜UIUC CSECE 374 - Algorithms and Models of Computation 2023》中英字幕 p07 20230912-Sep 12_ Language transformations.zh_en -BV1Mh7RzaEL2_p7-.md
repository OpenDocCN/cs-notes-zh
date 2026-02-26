# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p07 20230912-Sep 12_ Language transformations.zh_en -BV1Mh7RzaEL2_p7-

![](img/40ab0be7f376273748dfd8876866caaa_0.png)

。

![](img/40ab0be7f376273748dfd8876866caaa_2.png)

か。こ。成。啊，谢谢。😊，Yeah。Okay， let's go ahead and get started and thank you all for coming。嗯。A couple of。

Logistical things before。We get going with the real lecture one is I got some。Very helpful feedback。

From students and from TAs and CAs about the organization of the website and in particular people are having trouble actually finding things。

 so I've rearranged you know split things up into pages slightly differently and rearranged the menus。

 so in particular there's now just a page where you get links to all of the guided problem sets when they appear links to all of the lab handouts with the solutions。

 when they appear。Links to all of the homeworks seminar their solutions when they appear links you know about exams。

In particular。Um， there'll be， you know， some of these links are still placeholders。

 but right here on the exam page， you see links that point to like study problems for the midterms。

 things on prair learn to practice with。And so forth。

 so please take a look at the web pages and give me more feedback and please when I am in the front of the room talking into the microphone that means classes in session and at least two other people in the room are trying to listen to me so please keep the conversation down to a minimum while class is going on。

Thank you if you do need to have a conversation。Please step out of the room to have it。Thank you。

The other logistical thing is that there is a midterm coming up。In a couple of weeks。

And one of the things that happens in a class of the size when there are exams is that there are conflicts。

 I approved something like 20 different registration overrides leading up to the beginning of the semester。

 at least some of those people are going to have other classes or other exams at the same time that we have exams so there will be a conflict exam if you think you need to take it。

 there's a registration form that you can find linked here or on the exam page。Please fill that out。

By the end of next week at the latest so that we can figure out how many people we need to find rooms fors and things like that。

U。The justifications for taking conflict exams are listed in the student code。

 these are things like you've got another class at the same time。

You've got another exam at the same time， you've got a scheduled rehearsal or performance or regular employment at the same time。

 there are religious reasons why you can't take the exam at that time you have a dress accommodation that means it would be more convenient for you to take the conflict exam instead of the regular exam one thing I do want to emphasize is department policy。

This hasn't I haven't needed to say this in a few years。Gravel to job interviews is not an emergency。

So。That's not one of the reasons why we have to give you a conflict exam。

If we can accommodate you at the conflict exam， we'll do our best。But we can't promise。嗯嗯。And then。

The usual things， the weekly things guided problem set is up on Prairie learn。

 homework four is up on Prairie learn if you go。To a。If you go to find yourself。At Prairie Learnn。

 you can also find。Let's see。This is showing a bunch of stuff that you won't be able to see。

 but this is what you'll see， you'll notice in addition to the guided problem sets。

 there are a whole bunch of extra practice exercises covering almost all of the stuff we've seen in this chunk of the course。

Are we on the same page， are you with us， those are basic definition checking like here's a DFA or an NFA。

 can you recognize which strings it accepts？😡，The stuff down at the bottom is more like。

The guided problem sets。we walk through some sort of design problem there are a couple of things in here where we might ask you to write some Python code。

 we know that Python's not a prerequisite for this class and so I feel a little bit uncomfortable with this。

 but we do give examples of the kind of syntax that we would want in hopes that that will be useful。

 yes。Why is the GPS forpoing sense？After the G for N。换通 please。被错了。嗯。That's a very good question。嗯。

That's how it washed out we need to balance the material in。

We needed to balance the material in the guiding problem sets。s for the homework， yes。

 we weren't able to do that this time。Sorry。嗯。Okay。

I'm not also I'm not entirely happy with the fooling set exercises。

So I'm not entirely convinced how much preparation it would actually be。So I'm you know。

One of my other hats is I lead the team that writes these things。

 so if you have suggestions for the kinds of things you might want to see on Prairie learn that are different from what you see up here。

Please post your suggestions in the Prair Learn channel on Discord or in a discussion or talk to the CAAs or talk to me so that we can make this better。

Okay。think that is。

![](img/40ab0be7f376273748dfd8876866caaa_4.png)

All I want to say in terms of。Logistics， does anybody have any。



![](img/40ab0be7f376273748dfd8876866caaa_6.png)

呃。Administrative questions。Okay， yes。About to please。Bm。Probably over the weekend right now。

 you figure you're going to be spending time concentrating on the current homework。

That's probably a better use of your time。Also we need to like do the usual every semester revision to make sure that like we actually have。

Things that we're already on the homework and we need to label in the document as you've seen this in the homework。

 things like that。Okay。So。It will last few weeks。We is been talking about。Regular languages。And。

Last time I walked through most of the proof that there are you know three equivalent。嗯。

Representations for these things， you have regular expressions， you have DfaAs。And you have NFs。

And we kind of。Spent most of our time walking through the equivalence between DFAs and NFAs。

 and we saw the direction going from regular expressions to NFAs but probably a little bit too quickly to be really useful。

 we did not see this so-called state elimination algorithm to go from NFAs to regular expressions。嗯。

After some thought。You're putting the homework together。

You knowRevisising the GPS and so on and thinking about the midterm。

We're not going to ask you about the details of these algorithms in any homework or exam。😡。

So I'm going to skip over the last piece of this puzzle for the state elimination algorithm。

 those you are interested， I'm happy to talk， you know， answer questions about it。

 it's spelled out in gory detail in the lecture notes。😡，But I think our time is better used。😡。

Moving on。To something else and then。One of the pieces of feedback that definitely came back very strongly is Friday's lab was。

Frustrating and kind of pointless。So I do apologize for that。

 this is still a learning experience for me even though I've been doing this for a while。嗯。

Sorry about that， try to make the remaining labs， especially building up to midterm one where useful。

 so do want to spend more time on things that are going to be more relevant。

For the homeworks and exams。嗯。And I promise we're not going to make you like pretend to be computers。

Oh。Try to avoid that in this class。Okay，But the idea behind Klaney's theorem is you do have these three very different representations or apparently very different representations with。

Black box algorithms you can apply to move between them as convenient。😡。

We've also seen what are sometimes called。Closure properties。So closure properties are ways of。😡。

Playing with languages。That preserve regularity， so for example， if A and B are regular languages。😡。

Or any regular languages。A and B。I know that a union B is regular。By definition of regular language。

😡，so one this is one of the five cases in the definition of regularity。

 but I also know things like you know a intersect B is regular sigma star minus a or this is sometimes written a bar complement。

That's also regular。And so this means that。Regular languages are not only closed under unions。

 they're closed under intersections and compliments。

 and therefore they're closed under arbitrary bullolean combinations。😡。

So if I have five different languages。And I decide， you know， I want to。Right。Something like this。

 well that's only four。So I have an expression that looks like that。

uses some set differences and uses some symmetric differences there I know if ABC and D are regular languages。

 then this expression describes a regular language。

 even though it's using a larger vocabulary that we would normally use to。

Deefine a regular expression。And。The way we proved all of these。

Is using something called the product construction。嗯。So。

What I want to talk about today are other kinds of things that one can do with languages。

Like unions and intersections and so on。That preserve regularity。

And show that they preserve regularity in a way that's somewhat similar to a product construction。

 but a bit more general。Now， the way。That the standard product construction works。

AndSo if I'm given a machine that。It's called MA。Delta A。Machine M B equals。QB SB。

I mean to be some I want to show that， say the intersection of two regular languages is regular。

 I say， well， Pla Theorem tells me if languages A and B irre， then there are DFAs that accept them。

So I'm given DFAs。That。This accepts a。And this accepts B。I can build。The DFA。

Let's called that a prime。U prime， S prime， a prime， Delta prime。That accepts。

A intersect V as follows。Q prime is the product。Of Q A and QB。S prime is the pair SB。

A prime is the product of the accepting states of machine A and the accepting states of Ma B。

Delta of a little QB。Given a symbol A。Is the pair。嗯。Sorry。Delta a of QA。系。Don to be。Kly。B。So。Ungiven。

I've got these two regular languages that I'm calling A and B。😡，And I know nothing about them。

I'm not thinking of two particular regular languages。

 I'm thinking of two arbitrary regular languages。😡。

SoThe only thing I know about them is that they're regular。

 but one of the consequences of that is that there are DFAs that accept each of them。😡。

And I am sewing those two DFAs together into a larger DFA that accepts their intersection and the intuition is this larger machine that I'm building。

😡，Is simulating machine A and machine B running in parallel whenever the larger machine gets a symbol。

 it passes it to both component machines， it does the transitions that both component machines would do。

 and at all times it keeps track of what state Ma A is in and what state Ma B is in。😡。

And so the product machine's state is that pair state in Ma A， state in Ma B。

 that is the information that it needs to keep track of。😡，Hey。So this is。

The kind of game that I want to play， I'm given some language or some small collection of languages。

And I want to imagine some way of modify modifying one language or combining two languages。And。

Turning that into。A recipe for taking one DFA or a pair of DFAs。😡。

And transforming it into a machine that accepts the transformed language。😡，So let me give another。😡。

Sort of simple example。Let's say。Given。Any language。L。Prove that。Well。This one again。

If given any language any regular language L excuse me， it's not true for every language。

 it's only true for regular languages， given any regular language L proof that L star is regular Now this is a trivial example because I can literally just say。

 well， that's part of the definition of regular， but I want to go through the exercise in taking。😡。

A DFA for L in turning it into a machine that accepts L star。

 and we saw this really already as part of Thompson's algorithm。And so I'm going to start。

By saying let M。QS， don't sorry。A deelta。Be any。跌翻。That accepts no。Now， in this case。

I could aim for producing a DFA but it's a little bit more convenient if I allow myself to use some epsilon transitions。

 so I'm actually going to instead of building a DFA that accepts L Star。

 I'm going to build an NFA that accepts L Star。Okay， so we。Build。And NA。With epsilon transitions。

They'll call M prime。Q， prime S prime， a prime， delta prime。That accepts。L star。

And the intuition that you should have is。Here is my machine M。

Somewhere over here it has a start state。Somewhere in there， it's got one or more accepting states。系。

U。No， I don't know that the start states and the accepting states are different， no。

 I don't know that there are three accepting states。

 this is just the cartoon is just there is an Imana。The intuition of what I want to do。

Now I want to build some infrastructure around this。😡，That gives me an NFA that accepts the closure。

Of help。Can anybody remember how Thompson's algorithm did this？Yeah。

Join an excellent transition between said state Act fair statement。Okay。

 so one suggestion is you know， to put Epsilon transitions going from the accepting states back to the starts。

嗯。I think that will work in this case。嗯。Because I'm not trying to maintain the invariant that Thomasmpson's algorithm was maintaining。

 there's only one start， only one except。So。So thing。To build。And prime。Add epsilon transitions。From。

Accepting states。Back。To S。All， so I'll add an epsilon transition here。

I'll add an excellentps transition here。And I'll add an excellentps introductionulation here。

And now the idea is that in this larger machine。Whenever what the larger machine is doing。

 it's simulating the machine M that's given to it， whenever it reads a symbol， it does a transition。

 but when it gets to an accepting state， it says， well， I could，If I wanted to。Just stop here。

 stop the simulation of M here， say M has accepted the string that I've seen so far。😡，Cut off。

 you know， cut the input string in you know in。Cut a piece off the input string ending at the last bit I've read and start over saying。

 oh， well， as long as everything else I need to read is part of Lstar that I' am happy。😡。

Or it could non deterministically decide， you know what。

 I don't think this is the end of one of the pieces of L， maybe I should for a little bit longer。

So it has the nondeterministic option of taking the epsilon transition back to the start if it wants to。

 but it doesn't have to， and what it's doing here is out of all possible places that you might put a divider。

 it's guessing which ones are the right ones。😡，By deciding whether or not to take these epsilon transitions。

But if there is a way of taking the input string and splitting it up into strings that are in L。

 what will happen is the new machine M prime will read the first。😡。

First chunk that belongs to L and the machine M will end up in its accepting state。😡。

At which point M Prime wakes up and says， ah， you're done with the first piece。

 let me go back to the beginning。And then it reads the second chunk， M is in its accepting state。

 and prime says， ah， this is the end of the second chunk and it forces the simulation back to the beginning。

So what you get is。Qute prime equals Q。S equals S。A prime equals a。Delta of Q comma a is unchanged。

But， I add。Delta prime a Q comma Epsilon。Is。Either the set containing the start state。

If Q is in A or in the empty set otherwise。Now， it's really important to when you're thinking about this。

 remember that。😡，You have no idea。😡，What the machine M is doing。

 you have no idea what the language L is other than the fact that it is a regular language。😡。

The recipe for building this larger NFA。😡，Intuitively given by these arrows。

Works no matter what L is， no matter what M is。诶。But the other thing to realize here is what you're doing is you're treating。

The details of machine M， not as code。Not as a machine that does something。

 but rather its input data to an algorithm。The algorithm takes as input a DFA that accepts language L and produces its output。

A an NFA。That accepts L prime or L star just like。For the product construction。

 this is an algorithm that takes as input， the description of two PFAs， except two languages A and B。

 and produces output。The description of a DFA that accepts their intersection。

So this is the first time。That we're seeing something that's going to come up again。

More towards the end of the course。Which is that all code is data。😡。

You can view the description of a DFA as a program。😡。

But you can also think of the source code for that program as just a string of symbols。And。

Programs are pretty good at reading and strings of symbols and doing things with them。Yes。That。いた。

Could you say that again， please？当。Actually。Yes， you're right this is not accept this is accepting L plus not L star so I need to do。

Something else， I'm a little bit nervous。Doing an epsilon transition from the start state to these accepting states because those accepting states are also kind of in the middle of things。

 so what I'm going to do is just edit my thing directly。

My I'm just going to and I also don't want to make my start state itself an accepting state because there might be reasons to come back to it in the middle of my DFA this is the reason for having those extra epsilons outside and Thompson's algorithm so I'm going to add another state so pardon me。

Um。I'm going to have another state called okay， actually， no。

 I'm going to have another state called Epsilon。And。This is going to be an accepting state。U。

And then I need this to be。嗯。I need to update my。Epsilon transitions。

So I'll fix this after the lecture to put it in the right order。Yes， thank you。Yes。

You end up in it Saturday。Yes， they will go back to that。是。I you we started。还没上。你交干。

And after that不要嗯。Okay， so。What I really want to do here is to follow the way Thompson's algorithm did this。

Which is。Instead of going directly。What I'll do is I'll add a new start state over here。

I'll add a new accepted state over here。I'll put up salon transitions like this。

and put in loops so this this would this is the Thompson's construction and the reason for wanting to keep those separate from the original start state in the original accepting state is even though it's called the start state。

 it serves multiple it potentially serves multiple roles。In the DFA。

And it's fine to jump to it when it's to start state。

 but it's not fine to like jump in and out when you're kind of in the middle of things。Likewise。

 the accepting states， that really only play the role of accepting states when you're at the end of the input。

 if you sort of jump into the middle， then you're assuming something about the string you've already read and that it might not work out。

So just to be careful here the top construction worked except for the case when the string is empty。

 so I just specialcased it， but more generally I probably want to follow Thompson's recipe。Okay。

Let me。Let's try another example。对。So。Let me call this flip。嗯。We need to kind of function on strings。

😡，Hold flip。This is。does nothing if the string is actually empty。Um。If the string starts with a zero。

 then I replace that zero with a one and flip the rest of the string。If the stream starts with a one。

 I replace that one with a zero and I。Recrively flip the rest of the string。

 so this is bittwive's compliment exchange zeros and ones。8ight。

And now I could define a function on languages。So if given any language， L。I could。

Define this transformation on the language that says， oh， given any language， L。

 I can flip the language by performing a flip operation in every word， every string in L。

So this is the bit wise compliments of the language you like。系。So。U。Prove。That if L is regular。Then。

Flip of L。Is regular。U。Not。Too surprising。But if I actually wanted to write down a proof。Oh。

 would I do it？No。Induction， okay， good， that's usually a good answer， induction on what。Okay。

 so induction on the string， but you're not given a string。This is。The L is a regular language。

 that's the input to the process。A regular language。How do you do induction on regular languages？

is it点佢 just。The set up care Here debt。A language is a set of strings。😡。

A language is a set of sequences of characters。😡，All words， the Oxford English Dictionary。

 that's a language。Thank。All palindromes is the language。What。Yes。

That's the reason for the second definition here。So as an example here， so what is flip of。

Zero star one star。So this is strings that have some zeros followed by some ones。得。That's one star。

 zero star。They transform the whole language all at once。😡。

So I'm not doing induction on strings here because this is not a theorem about strings。

This is the theorem out about a regular language， I can still do this by induction。

 but I need a structure to do induction on。Yeah。Okay。

 so what is one way of representing a regular language？😡，The regular expression。

 regular expressions are structures that are defined recursively。

 that means you can do induction on them。😡，Because recursion and induction are the same thing。

 So I could do this， you know， proof。By induction。It's a， you know， let。Are the any。

Regular expression。such。That。The language of that regular expression is L。

And now I'm going to transform R into a regular expression。😡，Whose language is slip ofel？

And intuitively， you know exactly what to do。😡，Every time you see a zero in this regular expression。

 what do you do？You replace it with one。Every time you see it one in this regular expression。

 you replace it with a zero。Any string that matches the regular expression。

 the original regular expression corresponds。To another string where all the bits are flipped。

 the matches。The flipped regular expression in exactly the same way。Um now。嗯。

I could walk through the induction proof in gory detail， but the basic。😡。

The basic cases are going to be。呃。Something like this。R equals a plus B。F equals。嗯。recursively。

Flip a。And recursively。Slip B。R equals a dot B。F is recursively flip a。

And concatenate that with recursive leaf flip B。And R equals a star。Then F is recursively flip a。

And at a star。So in the base cases， I applied the function directly。

And that's not the right base case， sorry。For regular expressions， the right base case is， of course。

The empty set， not the empty string。If I get to down to a single string。

 then I apply the function to that single string。If I'm in any of the recursive cases。

I applied this algorithm recursively to the components and then joined the components in the right way。

And hopefully it's。Fairly intuitive why this works。

The induction ferry makes it work in each of the pieces and I put the pieces together in the right way。

 yes。No， no problem。对的。I'm defined enough。F is the regular expression for the flipped language。

Than a building F is the output。Yes。The offer is at the last。Because I'm not flipping strings here。

 I'm flipping regular expressions。I'm flipping languages。Questions。

 why did I write the last flips in uppercase instead of lowercase。

 just as a mnemonic to remember that I'm doing this to languages and notstrs yeah。不是。こ关。啊那个租个使用嘅。

These five operations are like。You can't just boost one of them and then just say， oh。

 the other ones using this we the definition of a regular expression is it's one of these five things。

So any proof about regular expressions needs to be， given a regular expression。

 it's one of these five things。And in each of these five cases I do the following I mean if I were writing this out carefully。

 I would say， okay， by the induction hypothesis there is a regular expression a prime that represents flip of a。

 by the induction hypothesis there's a regular expression B prime that represents flip of B。

 so I'm going to output flip of or a prime。 B prime。And there'd be more details in there。

But we can also。Do the same thing if you're not comfortable using induction。By transforming a deal。

Okay， so I could do this。followsollows， so let M。Q S。A deelta。Any DFA。That it accepts cell。We build。

DFA。And prime。Q prime S prime a prime delta prime。That accepts。啱妈。Flip ofel as follows。

Q prime is the same as Q S prime is the same as S a prime is the same as a。

And Delta of Q delta prime of Q comma 0， delta prime ofq comma 1。This is what I need to change。😡。

So I'm not changing the states， I'm not changing the accepting condition。

 but I do need to change how the transitions work。So in this new machine that I'm building to accept flip of L。

When I get a one。What should I do？I'm sort of simulating the machine that accepts L。

And keeping track of that machine's other state。So when I get a one。

 what do I want to pass to my simulation？Zero。And so how would I write that down？

In terms of the output of these， the new machine transition function。

So the new machine is in state Q and it reads a one。

What happens in the simulation of the original machine？Well the original machine is in state Q。

 and I pass to the zero。Right， likewise。The other way around， if my new machine reads zero。

 then I should pass a one to my simulation of the old machine。So this is a little bit， you know。

 sometimes kind of hard to wrap。Um， certainly it wass hard for me to wrap my head around the first eight times I saw this。

 what you kind of want to do is have a machine that reads in the entire input。

Applies the flip algorithm somehow， and then at the end。

 after it's completely transformed the output， feed it to the original machine M as a separate protein chain as a black box。

😡，You can't do that， the rules of the game are when the machine that you're building reads a bit。

 it has to do everything and with that bit， and then when it's done says okay， give me the next bit。

 there's no going back， there's no making multiple passes。

 there's no transforming into a temporary array and then feeding that temporary to a subbrity。😡。

You have to act on it now。So what it's really more like is your best friend is standing next to you and your best friend has been training for 25 years in the mountains of Tibet to accept a particular regular language。

😡，And you walk in and go， well， I can accept the flip of your language。

And how do you do it when somebody tells me one， I got zero， when somebody tells me zero， I say one。

And the says what the end of the input， what're the end of the input， except， okay， Excel。

This is how you win against grandmasters playing chess。

You play one of them white and the other one black。

You have to make the first move white pondnda King ford， that's a good choice， then you wait。Oh Saar。

 you wait for the grandmaster who's playing white against you to move white， okay。

 he says Ponda King4 great pondnda King4 and then this grandma makes its countermove。

ing for okaying for okay and this grand master moves a night okay， great。

 I'm going to move a night over here I know they're not both going to beat me。😡。

I just stand in the middle of this， that's what I'm doing。

 I'm standing in the middle between the real input and the real machine。😡。

When the real input tells me zero， I tell the real machine one。And vice versa。Hey。

 this is just formalism for how to do that。开。Let's try one more。So。

Let me be consistent here and just call this revv。啊嗯。So the reversal of a string is。

Exactly what you think it is， I take the characters in the string and I write them in a reverse order。

This is how it's defined recursively， the reversal of the empty string is empty。

 the rust of a string with an A at the beginning is obtained by recursively reversing the rest of the string and then gluing an A on the end。

哎。And then I can define the。😡，The reversal。Of a language。As well。

 reversal of the string for every string in the language。Okayy。😊。

So just so we're all on the same page here， what is the。Reerssal of zero star1 star。

But I take a bunch of all strings that have some number of zeros followed by some number of ones。😡。

One star， zero star。So the reversal of 001111 is 111100。So the zeros。

 when I reverse the string move from the beginning of the string to the end。

The ones move from the end of the screen to the beginning。

This is exactly the same thing that F did for this particular language。

 but that's because of this particular language。😡，Maybe a better example is。What is the reversal of？

Zero1，1。Star。This is 110 star。every one of those01 ones gets flipped and then they get catcatenated together in the wrong order。

 whereas。One1 star would have given us one0 zero star。Okay。So I claim。😡，Optimistically， that。

For any regular language。L。I want to prove that the reversal of L。Is also。Regular。

Because this is a bit strange because by definition。

DFAs read their input strings one bit at a time from left to right。😡，No exceptions。

But if I wanted to like pretend to simulate。At DFA。

 I'm essentially having to force that DFA somehow to read the input bits one at a time from right to left in violation of the rules。

So。First glance it may not be entirely clear how to proceed here。嗯m。

But there are two approaches I could use one is。😡，I could pull out my trustee friend。

 the induction fairy and do this with regular expressions。And this。

 I mean there's a bunch of boilerplate stuff to write down， but the one thing。

 the one step in the regular expression proof that's interesting is if your regular expression has the form a dot B。

 then the reverse regular expression has the form reverse B dot reverse A if to remember to reverse the order of the concatenation。

 otherwise it goes through， but I think the more interesting way to do this is with。😡，DFNs so。

Any any。DFA。That accepts。Helf。We build。And I'm going to give a begin here， I'm going to build an NFA。

And prime。Q prime S prime， A prime Delta prime。That accepts。The reversal labelelle。As follows。

So I can't walk into the formal symbols about having some intuition about where I'm going。U so。

Maybe just you know， to develop some intuition。Let me just。Start。With。嗯。A stupid example。I say。

 I have no idea。What this DFA does， I just broke down a bunch of arrows。ok。Um。U。Most ideas are bad。

 so it's really important to have lots of ideas so you can get through the bad ones。

Can somebody give me a bad idea？For how to reverse。This is UFA。You've heard from you a bit。

 so let me give a couple of the people a chance， yeah。Flip the transitions。What a strange thought。

We' see what would actually happen， well， this the arrow never is out。嗯。This one goes here。

 this zero goes there， this one goes there， this zero goes there。This one goes there。

 this one goes around， but it goes around clockwise。嗯。How do I reverse？呃。acceptcepting state。

But wait a minute， if I'm reversing the arrows。That means that in the in my transform thing。

 I want to start where the old machine would end。Kind of， maybe。

 and I want to end where the old machine would start and so， I'm going to make this a start state。

 I'm going to make this accept state。Okay， let's sit back， what is this， oh。

 this isn't a DFA anymore。😡，Because if you look at the state on the bottom right。

 it's had two1 arrows coming out of it and if you look at the state on the far left。

 it has no one arrows coming out of it， so this isn't a DFA anymore。But on。This is right。

This is correct。Okay， so let's let's watch what happens if I you know read the string here。

 so let's say a10。1，1。嗯。Right。So I'm going to give these states names S， A and B。

So I'm going to go from S to A to B to B to B。Okay。

 so I'll call this S A B so now what happens if I if I attempt to read this string in the reverse order here。

 well， I start and say B， one of the things I can get to when I read a one， I don't have to do it。

 but I can is stay at B。And then for the second B， I can also state at B， and for the third B。

 you know what， actually this time I'll go to a， and then for A， when I read a 1。

 I have to go to S and that's the end。S is an accepting state。

 so I managed to get from the start state to the accepting state， so yes。

 this is a string in the language that I want to accept。😡。

And I got there by just reading the string in reverse order。

So it seems that this NFA on the right accepts the reversal of every string that this DFA on the left accepted。

诶。嗯。Now， the somewhat harder trick is to show that I'm not also accepting other things。嗯。

But you can play the game in reverse， you can say， oh。

 if I've got a string that's accepted by the NFA on the left。

 that means I have a sequence of transitions going from left from right to left。

If I read that same sequence of transitions from left to right。

 it's a path from S to the accepting statement in the original DFA。Okay， so。This works。

Reverse all the transitions。Hey。Cool， now we just have to write it down。How do we actually say this？

Well。All right。So what are the states？Of this new NFA that I've built over here on the right。It's Q。

 it's the same as it states of the DFA that I started with on the left。U。

Where do I start the NA on the right？Yes。Right， so in this case。

 this is one of those cases where I really want to have multiple accepting states。

So I'm going to own it and just the idea of mold to pull。Multiple。Start。States。Remember。

 I'm allowed to do that because I can。Pix it up later if I really have to。Okay， so。

What are the accepting states？😡，Of my new。NFA。It was only the start state of my original DFA。诶。😊。

And now for the difficult one。In my new NFA， if I'm in state Q and I get the symbol A。

What states can I move to？Over here。And how do I describe that in terms of the transition function that defines this DFA over here on the left？

So intuitively， I want to say， okay， I'm simulating running this machine over here on the left backwards and I'm in state Q。

 and I read say a zero， I want to go backwards along some zero arrow that enters state Q。

 but I don't know which one。😡，So I'm going to try them all。

 so all states P such that delta of p comma a is equal to Q。Right。

It's tempting to write this as like the inverse transition function， something like that。

 but don't I。ThatThat's trying to be a little bit too clever with the defin the with the notation。

 just write it out like I can transition in my new NFA。

To any state P that in my old DFA had a transition going into Q with the right label。😡。

And that there I'm done， I've described this intuitive picture for this one example。

 but now in more general terms for any regular language，😡，Represented by any DFA that accepts it。

And I'm really exploiting the power of nondeterminism here because if there's more than one incoming arrow with the same label。

 when I reverse， there'll be more than one going arrow with the same label yeah。

then we going to do some things。it is the same underlying number of states。Okay。

 this is a good question， the examples that I've shown you so far with one exception。

 the new states of the new machine I'm building were exactly the old states the old machine I started with。

That one exception， though， was the product construction。There I'm given two sets of states。

And I combine them to get one set of statess that's a set of pairs and I am going to walk through one more example。

That is a bit more difficult。Where you have to do something more interesting with the states and you have to do something more interesting with the accepting states and so on。

So u。No， it is not always the case that you're going to end up with the same states and some simple swap or keep the same started in accepting。

嗯。At least when I was first learning to do this。The hardest part for me was first coming up with the right intuition。

And then figuring out how to express the new transition function。😡。

So that's part of the reason I'm concentrating on this here。

 and part of the reason why in lab tomorrow， you also have be concentrating on that particular piece of the construction。

As I think。That seems to be at least one of the places where people struggle the most。Yeah。

this is right suitable。And then。Just use that as。So the question is。

 can you write the pseudocode for this？I'm not entirely sure what you mean。

Because you're given a DFA。The only way that I know how to represent an arbitrary DFA is through this formalism。

So even if you're expressing the transition function in some not in this mathematical notation thing。

You still need to write it in terms of the original states Q and the original transition function。

 little delta。😡，So it may end up being clearer to express the new transition function as some more pros。

But it still needs to be precise。Um， and then the not necessarily the easiest way to write it down。

 but the most concise way to be precise is to use the notation。Yeah， there's a question back there。

Yeah。暂时。I。That correspond。1，0，1。Yeah， so I should have maybe written this a little bit more neatly here。

What I meant here was this is 10，11。No。All right， let me do this for real。

Thank you for asking that question， us could go to A on a one。it goes to a and zero。

 it goes back to s and one， it goes to a and then one， it goes to B and another one， it goes to B。

And in the reversal thing， go SA， A， S， A， B， B， but now I'm transitioning backwards。Okay。

So in the last 10 minutes， let me show you one more。

 this is using nondeminism in a fundamentally more interesting way。😡，So。This is。The language。

Pa one of L。So。This is。The set of all strings W， such that W dot W reverse。

 actually let me stick with the notation I used earlier。W。t reverse of W。Is in L？

This is the first half of every palindrome in L。Notice what this is not。😡。

This is not L dot reverse of L。😡，No， that's not what this means。

That is absolutely not what the means。This says that if my language L happens to have any even linked punds。

😡，Then the first half of each of those palindromes makes up this new language Palinov L， Palin of L。

 if L has no palindromes in it or it only has odd link palindromes， then pallinovl will be empty。😡。

Okayy。😊，So。But more， you know as an example， if zero1，101。1，0，1，10 is in L。Then zero， one。10， one。

Is in。Aannabel。Because。This is。Oh。01101 followed by the reversal of 01101。That string is an L。

 so those the first five， the first half。Is it out？

So I've got a machine sitting over here on the side， so I'm given a DFA。

 M the Q start state accepting state transition。😡，Be any DFA。嗯。Accepting。L， and I want to build。

An NFA。And prime。States。Start， accept transition。Um acceptcepting。Helenelle。

But before I go into any formalism， I need to。U。Think about what I'm going to be trying to do。

So when I'm reading the bits of my word W。What I actually want to imagine doing is treating each the incoming bits both as the starting bits going from left to right at the beginning of WW reverse and as the bits at the end coming in order from left to right to left in reverse order。

😡，In some sense， I'm going to be building a product。Of L and or sorry of M and M reverse。

 where M reverse is that machine that NFA that I built。

A second ago to accept the reversal of the language。

So I'm going to be calling this machine over here for L feeding in the bits one at a time in the order that they arrive。

 and I'm also going to be feeding those bits at the same time to this machine MR that' the reversal of L and saying you pretend you're reading these from right to left。

But now I have to think where do these machines start， well。

 the original machine for L starts in its starting state， but MR starts in the accepting states of N。

😡，And then when do I want to accept？😡，ButBas， I want to accept when these two machines。

 when the smoke clears and the input is done， I want to accept if these two machines have kind of met in the middle。

😡，At the same state。A。So。嗯。Q。Q prime is going to be Q cross Q。I'm going to keep track of。

Two different states in my original DFA or in states in two different copies of my original DFA。

My start state， actually my set of start states。So with multiple starts。Is going to be。Well。

 this is going to be like all pairs， F comma。S prime where S prime is in A。

So the machine on the left is going to start in the start state of M and the machine on the right is going to start in one of the accepting states of M。

 of which I'm going to guess nonderministically。The accepting states。This is going to be， well。

 I'm going to accept if in the end， both my forward machine and my backward machine land in the same state。

😡，So the machine that's reading the front half of WW reverse in order from left to right ends in the same state as the machine that's reading the back half of WW reverse order in reverse order from right to left。

😡，They meet in the middle。U。And then， well， I need to describe my transition。

So if I'm in state Q in my forward machine and the state R in my reverse machine。And I read state A。

Then what am I going to end up in Well， the forward machine I know exactly what it's going to end up in。

 it's going to end up in the， you know， I just pass the bit A to my forward machine。😡。

And it applies the forward transition function to that state。

But I also need to deal with the backward machine and so I need to drive the transitions on the backward machine backwards。

😡，So I'm going to go back to。Any state P such that delta of P comma a equals Q。It makes to make sure。

Yes， okay。Except no， not P。Thank you thank you。Or。Okay。😊，So。

This is a much more complicated version of this， where I'm really using nondeminism like to its complete extent。

😡，the original copy of the machine interviewer on the left is just taking the bits in one at a time and simulating again。

But I've got another copy of that machine M running backwards。

 I guess the accepting state that I start running backwards from， every time I read in a new symbol。

 I guess which transition to follow backwards。😡，And as long as there's a way of guessing correctly going backwards through this machine。

 and I ends up in state Q， and at the same time， the For machine ends up in state Q。😡。

The forward machine has read W， the backward machine has read。The reversal has read W。

 but read it backwards。So that means I'm going to have a complete sequence of transitions going from my original set S。

YouQ， this is through my original machine。嗯。Let's call this some R accepting。

And this is going to go through the Veral machine so 01。

10110110 so I feed in the pallin machine the five bits 01101 normal evolution happens over here on the left on the right backwards01101。

And if this all works。That that means in my original DFA。There is a sequence of transitions。

That follows the entire palindrome and goes from a start state to one of the accepting states。Now。

I expect a lot of you will need some time to digest this。😡，I would recommend。Taking this example。

 playing with a few specific DFAs， maybe two states， three states。

 and seeing what you get out of this， whatever out of building this product construction and convince try to convince yourself that it works。

 to understand how nondeterminism is sort of the key idea that makes this thing all work。嗯。

If you didn't get it immediately， that's fine， neither did I， but we'll come back to it again。😡。

He thanks to see you all on Thursday。Im talking about the lab last tried to put the slides yesterday evening。

 so I just blog in the exam we should be able to do all like NFA to the DFA to regular expression and regular expression to NFA。

😊。

![](img/40ab0be7f376273748dfd8876866caaa_8.png)