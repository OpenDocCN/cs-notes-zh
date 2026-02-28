# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p02 NETS 4120_ Algorithmic Game Theory, Lecture 2.zh_en -BV15kLRzTExU_p2-

![](img/f475a97a40833d02824bfd191928093c_0.png)

啊你我你啲水。Okay， so I。😊，就都喺度。All right， welcome to Le two。What are you guys。

 quick quick raise of hands how many people believe themselves to be registered for this course？😊。

Yeah。Okay， it's like a good number。嗯。Cool so maybe sort of a quick administrative note before we dive in so the first problem set is out if you are on the slacklack you have been notified of this and also if you like go visit the course website you can download the first problem set it's due in two weeks on gradecope if you are not on the Slack you should send me an email and I will add you to the Slack everyone feel comfortable in their ability to find the problem set do it and then turn it in on gradecope in two weeks。

Awesome， like a confident class。Okay so first order of business as you recall there was you know like homework zero was to participate in this guest two thirds the average game from last class as of 8 a。

 this morning I you know tallied the results I gather it doesn't include absolutely everybody。

 but let's see how you did。As of this morning the average remember the rules right you have to enter you know a number it doesn't have to be an integer between zero and 100。

 we had a web form for this what I was going to do is compute the average。

 it was a little over 13 and your goal was to try to be closest to two thirds of the average。Okay。

 so the average was a little over 13， two third of the average。

 I've done my mouth right was a hair over nine。😊，Someone guessed 9。11， which was the winner， Jack。

 is Jack in the audience。He it can be 10 minutes late， I've got $5 for him， but okay。

Let me know when he enters。It。What is your name？When Jack enters。

 can you like just shout out like here's Jack and I'll handle okay。Okay。

So I just want to like think a little bit about this game okay and then on the homework you'll see you have to prove something about it but。

If you think about this game right like like the strategy space is you enter like a number between0 and 100 right so like the average like even in the worst case even in the worst case where everyone you know like doesn't think about this game at all and they like enter the largest possible number 100 the average can't be of course bigger than 100 and so two thirdds the average can't possibly be bigger than 66 so like like it would just be a mistake to have entered a number bigger than 66 like that is what will when we see the definition today that is what we will call a dominated strategy like if you entered something bigger than 66 like that was just a mistake you should have lowered。

Your guess and and that could only have done better。

 even if everyone else in the class was maximally stupid and like entered 10 right so like entering something。

Above 66， that's just a failure of your own rationality independent of what you think other people are going to do Okay。

 good nobody did that as of this morning。Now you can like go like another level down， you can say。

 okay， well。You know I'm pretty smart I know that's like a you know a winning answer is going to be below 66。

 but I don't know about all of those other people in the class like maybe they're all super dumb they're going to enter 100 in which case。

You might right like 66 is not like an impossible answer。

 you could win entering 66 if everyone else entered 100。

Or you might think you know this is like a class at Penn like these kids are pretty smart。

 they're probably going to have realized that there's no way to win by entering something you know 66 or higher so like nobody's going to enter anything I think nobody in this class it's going to enter something above 66 and if that's true of course。

 you know then the average can't be the average can't be higher than 66 and so two thirdds of the average can't be higher than 44。

and so okay， nobody entered a guess above 44 either。

 which means not just are you guys reasonably clever。

 but you think that your classmates are reasonably clever as well， at least。At one iteration。Now。

 of course， if you think that all of your classmates have gone through the same chain of logic that you have right。

 so none of them are going to enter a number above 44， you might think， okay。

 well the average can't possibly be above 44 if they're you at least one you know。

 level depth cleverness， in which case， like if that were the case， nobody would enter。

 either there wouldn't be a winning guess above 29 and a third。Okay。

 we did see and now we're starting to see some guesses， we did see one above that。

 which is not us right the person who entered this is not that they've you know right it's not that they're not smart。

 it's that they think you guys aren't as smart as they are。Right。you know。

 and you can keep going right like the number of you who think that we're going to youre going to continue this lot。

 you know， the number of you who think that your classmates are going to continue this logic you know。

 at depth four， okay， it's growing right at depth at depth five， you know， it's even larger。😊，Okay。

And of course you might have thought that your classmates were all maximally rational right that we would sort of continue this induction all the way down to zero right。

 I mean， you know eventually if everyone's like maximally rational you know and assumes that their classmates are and assume that their classmates assume that they are and assumes that their classmates assume that you know。

Each other， so on and so forth， it's kind of like the islanders problem you guys thought about。

Really， the only winning guests can be zero。And three of you thought quite well of your classmates。

 but of course， you know， they didn't win。Okay， so so anyways。

 you know when Jack enters the room I've got $5 for him。

This is maybe just to sort of we're going to talk about iterated elimination of dominated strategies today。

 and this is just maybe to get you thinking about， you know。

 whether we really believe the predictions that it makes。Okay。

 so that was the game we played any questions about this？Okay。So。What I want to do today are。

If you've taken a game theory class before， review many of the basic definitions of game theory that are going to underlie sort of what we do this semester and if you haven't taken a game theory class before。

 maybe you're seeing them for the first time， but they're not that complicated， so what'll be find。

Okay。So we're going to talk about games and what they are。

 we're going to talk about what a best response is。

 we're going to talk about what a dominant strategy is。

 and we're going to talk about iterated illumination of dominant strategies which is the kind of logic that you might go through similar to how you might think about how you'd play this guess the two- thirdds。

 the average game to try to make predictions about what maximally rational opponents might do。

And we'll talk about solution concepts there's going to be a bunch of solution concepts you know like if you get really lucky everyone has a dominant strategy。

 we can talk about a dominant strategy for Libria we can talk about。You know。

 if you get marginally lucky and there's a unique solution to this sort of iterated elimination of dominated strategies kinds of ideas。

 and we'll talk about Nash equilibriumria and the relationship between these things and。

This will be sort of the beginning of what will be sort of a longer。

Theme in this class of thinking of hierarchies of solution concepts that try to make fewer and fewer assumptions。

Okay， so that's the plan for today。嗯。Any questions about？The plan or course logistics or。

And Jack is's going to arrive or anything like that。O。Okay， so okay。

 it's a game theory like we're already on lecture two I better tell you what a game is so what's the game。

😊，嗯。😊，So a game is going to be， you know， okay a model for an interaction。

 but really some mathematical object that's going to be defined by a few things。Okay。

 what are those things？First， there's a set of players。Okay， think of this as a finite set for now。

 the players intuitively are the agents that will be interacting in the game， whatever that means。

All right， P for players。Now。If it's an interaction。

 the players had better be able to do things and we will give a name to the set of things that each player can do。

Okay， so that we'll call that the action set for each player。The action set for player I for some。

 let's imagine the players are just like indexed by integers or something， so we can say player one。

 player two， player three， so on and so forth， the action set for player I。

 I will write AI and think of that as just some finite abstract set for now。

 it could be like rock paper or scissors or you know any other set of actions depending on what the game is the name of the actions don't really matter right but their cardinality does。

And。It's going to be convenient for like we're going to have to talk a lot when we talk about games about sort of。

What I'll call like a game profile， which is like。The set of actions chosen by all of the players。

Okay， so like， you know， when we start talking about game dynamics。

 players will be choosing an action， each player will choose an action and an element over their set AI。

If we have end players， they're all going to do that。

And it's going to be convenient for us to think about。U。

The vector of actions like this N2 pool of actions that corresponds to the choice made by each of these end players。

Okay， and just to like introduce some notation， the space that that will live in like this vector of n actions。

 this like action profile， a choice of an action one for each of the players。

 I'm going to call that a。And that's just the Cartesian product of the action set for each of the end players。

 which just means， you know， what kind of object lives in a。Well， it's a vector。

The length of the vector is equal to the number of players。

 every player I has their own coordinate in this vector。

 and what the vector records in coordinate eye is just the action chosen by player I。Okay。

More notation。It's going to be， you know， since we're talking about like strategic decisions by players。

It's going to be handy for us to talk about you know， when we zoom in on some particular player eye。

 we're going to have to like think about。What action should she choose， what should player I choose。

 given what everyone else in the game is doing？So it's going to be handy for us to zoom in on particular players and talk about。

The choices。That all of their opponents are making。Okay， so when we zoom in on player I。

 what will be of interest to her when she is choosing what action to take is the。Set of choices。

 set of actions chosen by the n minus one other players other than her。Okay， so what is。

That object look like it's a vector。Of length n minus1 rather than n。

 it has one entry for every player other than her， she hasn't made her choice yet。Okay。

 and the space that those vectors live in。I'll call that a minus I。

 the notation is sort of meant to evoke that I am excluding player I。And what is that space。

 it's just the Cartesian product of the action set。

 A J for each of the players J other than player I。So a vector。

 you know an action profile in a minus I， what does it do it specifies an action for everyone other than player I player I's action is undetermined by an action profile in here。

And what kind of object is that it's a vector of length n minus1。

 it's got a coordinate belonging to every other player J， there's n minus1 other players J。Okay。

 so that's notation， but i'm going to use it a lot。

 so if it's if you have no idea what it could possibly mean please ask now because otherwise the class will be extremely painful for like the next semester。

So notational questions。Okay， good。And okay， finally like。

The basic premise in game theory is that people will be trying to choose actions so as' to maximize their own utility。

And so。To specifyify a game in order like for that to like even begin to make sense。

 I need to be able to tell you what are the preferences of each of these players。

 what maximizes their utility。Now。What are the kinds of things that players can have preferences over well you know like the only thing we've defined is that players are going to choose actions and a state of the game corresponds to a choice of action for each player that's this thing that i'm going to call a play profile that lives in the space a。

And so that's what。Players care about so a utility function for player I and each player will have their own utility function。

 maybe a different one，s people's objectives can be different。It's just some function。

Labelling every possible action profile with a real number。Which you should think of as saying， okay。

 you know， how happy am I， you know， if the way things shake out are that。

We're playing some action profile little a okay so so for each of the for each of the exponentially many ways that the end players in this game might choose their action right there's exponentially an n many different。

Combinations of choices， the utility function tells you numerically how happy player eye is with those actions。

Okay， so this is just some function mapping A， the set of action profiles to real numbers。Okay。😊。

Makes sense。Okay。So the basic premise in game theory and you know。

 like of course this doesn't make sense yet we're going to have to unpack you know different ways you can try to formalize this premise and what what predictions mean。

 but the basic premise is that，Players are going to act so as to maximize their own utility。

 okay so like。You know， my utility function in a game sort of guides。Somehow， you know。

 how I'm going to play the game and I'm going to try to play the game whatever that means so that。

I get a big number out of this utility function。Now I only， you know。

 the utility function is a function of what everyone else does。 I only directly control what I do。

 not what everyone else does。 so you know， I have。I can't just like unilaterally like。

Assert that the state of the world is going to be the thing that maximizes my utility。

 I can sort of I can make choices for myself， but I can't control what others do。Okay。

 but my like my basic goal is going to be to try to like maximize my utility set。Clear。

And so we can try to formalize that a little bit， I mean， of course， like I can't。I can't。

 it doesn't make sense to like directly maximize my utility because my utility is a function of things that I do not control。

But。You know if。If somehow everyone else told me。What they were going to do。

Then it would make sense to think about the thing that I could do。

 the action that I could choose that would maximize my utility。Reja， yes。You won $5， yeah。

 so you can count it if you want。I trust you， okay。

 I hope this by is a good teaching review at the end hopefully。是这个。Okay， good guess。So。

You were supposed to tell me when Jack walked in。嗯。Okay。

 so like it doesn't make sense to like maximize my utility like。

 you know from whole cloth because my utility depends on things that I don't control。

 but if I knew what everyone else was doing， then maximizing my utility would be like a well defined problem。

Okay， so here's like a concept that's going to be core to lots of what we talk about。

 it's what's called a best response。So suppose in me， player I。嗯。Knew what actions。

All of my opponents were taking Okay， so I knew the sort of action profile that I'll write a little a minus I。

 which lives in this space I just defined big a minus I。

 which remember is a vector of length n minus one that tells me the actions that are chosen by all of my opponents。

嗯。Okay。Then my best response to that set of actions， the action profile of my opponents。

 would be to choose the action AI that maximizes my utility given what everyone else is doing。Okay。

 and just sort of sneaking in another bit of notation here。Remember。

 the utility function takes as input of vector of length n。

 specifying like a choice of action for all end players。What we've been given here。

 the objects that we are best responding to， we are defining a best response with respect to is a vector of length n minus1 specifies the actions just for the n minus one other players。

But if I have an action A for player I。And。An action vector。

 a minus I for the n minus one other players。I'm going to just write a comma a minus I to like stitch those together into a full action profile specifying an action for all N of the players。

The n minus1， other players and me。And that's a thing that I can plug into a utility function。

Okay and so the best response to the choice of actions of my n minus one opponents is defined to be just the action that maximizes my utility when I plug it into my utility function together with the choice of action for the n minus one of players。

Does that make sense？Okay， so。Yes， so like you know our basic premise agents are going to try to act so as to maximize their utility okay we have to like think about what that means。

 but like。We're going to start thinking a lot about best responses， maybe if people are playing well。

 then I should be best respond， you I'm not going to necessarily get to the game state that is my absolute favorite。

 like I can't control what other people do， but I can control what I do so maybe I should be best responding to what everyone else is doing。

And maybe other people should be doing the same， yeah。这条。当ction。And I is。不意思。Yes。

 so we could just be given one， I could say like you know。

 here's an action profile it lives in this space capital a or if I'm given an action sort of this sort of partial action profile that specifies the action of everyone else other than player I and then I'm also given maybe I should have written like a little eye here。

 if I'm also given an action for player I when I just write something like this。

You interpret that as you know stitching in the one missing coordinate of a minus I in the right place and together this specsifies an action for all N of the players。

 does that makes sense。Good question。Okay。Okay， so nobody has asked this yet。

 but last semester someone asked this and it was a pretty good question right I sort of say okay like you know heres like here are the basic axioms that we are going to like base the rest of the course on people are just going like singlemindedly maximize their utility you can ask okay like is game theory just for like sociopaths like is there no you know I'm just like am I like am I modeling like only like you know hedonistic agents that care only about like their own like well-being and not like you know anyone else and the answer is no right like。

I have made no presumptions at all about what your utility function is your utility function could be anything right like in choosing to model some interaction。

 if you want people to sort of you know have high utility when everyone in their city is well fed and well housed and that's fine right like there's nothing saying that your utility function has to take large values for states of the game that sort of correspond to you getting stuff or whatever。

Your utility function could be anything。The utility function is just a concise way to record what your preferences are over outcomes。

 if you prefer some outcome over another we just encode that by saying you have high utility for that outcome。

And so we're not really assuming that people we're not really assuming at this point anything about people's preferences。

 only that they have consistent preferences over outcomes。Now of course。

 when we start studying actual games and trying to make predictions within those games。

 the modeling decisions that we have made in those games in deciding， for example。

 you know who the players are， what the action sets are and what their utility functions are okay those modeling decisions will have content about how we believe the world might work。

 but the。Framework itself does not just because we use the language of maximizing utility。

 that does not mean that we are making the assumption that people care only about themselves and not about others。

 that would be an assumption that would be made by a particular choice of utility function and not by a different choice of utility function。

Okay。Does that？Makes sense questions about。This。I mean I guess it's like you guys already registered for the class so it's like who are the people who showed up。

 I guess either you sort of think game3 is not just for sociopaths or like you're fine with that like that's but maybe that's what like caused you to sign up。

Okay。So what is the general？Idea we're going to try to take games and we we're we're going to try to like。

Think about different ways in which we might predict。What might happen in those games？Okay。

 and the general idea is that。You know， all of this willll need to formalize， but like you know。

 in stable situations， whatever that means。All of the players should be playing a best response。Okay。

 so if we're sort of imagining that you know， people the world is messy。

 people are going to you know start playing these games。

 will'll take some time probably for people to figure out what they're doing for play to stabilize。

 but like if that ever happens， if play like stabilizes and people are sort of consistently doing something。

And in stable situations， everyone should sort of be playing a best response。

 they should be more or less playing the action that maximizes their utility given what everyone else is doing。

And it's。Sort of toutological。If that weren't the case。Then the situation would sort of。You know。

 if people had even a little bit of cleverness would not be stable because there would be people there who would look around and say。

 look， you know， given what everyone else is consistently doing because we're supposedly in this stable situation。

 I am doing something that is suboptimal according to my preferences。

 so I should change what I'm doing。But if people start changing what they're doing。

 it's not a stable situation。Okay， so like， you know， so far。嗯。😊，Yeah。

 statement like this is sort of agnostic to whether there are any stable situations like maybe you know play just never stabilizes in one of these games。

 but if it ever does， if we ever reach a stable situation， you know then like。

It seems reasonable at least you know， in English before we try to like write this down in math。

 that people should be， everyone should sort of be playing a best response because to each other because if that wasn't the case。

 it wouldn't be stable。Okay， so that's maybe sort of like high level。

Guididing idea that's going to be behind a lot of the particular solution concepts that we talk about today and over the course of this class。

O。mQuestions about。This general。Guiding principle。Okay。

So what do we mean by stable solutions and like？When can we assert that they exist？So in general。

What makes it hard to think about what action you should choose if you are a player living within a game？

Is that your utility depends on what other people are doing and therefore what your best response is depends on what other people are doing and so if you don't already know what other people are doing。

 it might be hard to think about what you should do。But if you're lucky。

 like you might find that there are like some actions that you can eliminate right off the bat that just like never really makes sense。

Okay， because maybe there's some other action， some other fixed action that no matter what other people do。

 would always be at least it' good and would sometimes be better。

And if we do have such a pair of actions， A and A prime。

 such that A is always at least as good as a prime and sometimes better。

 no matter what everyone else does。We say that your action A。Weekly dominates。

Your other action A prime。Okay， what it means is。No matter what everyone else does。

 you might not know what everyone else is going to do。

There's no situation in which it's better to play a prime than a。

And sometimes it's better to play A than Aprom。Okay。

 so writing this down a little bit more precisely， if we say that a weekly dominates a prime。

 that means that。No matter what everyone else does。

 for every profile of actions that might be assigned to your opponents， the other people in the game。

If I look at the utility that I get by playing A and I compare that to the utility that I get by playing a prime。

 I always get higher， at least as high utility playing A。And。I'm not always indifferent。

 like there's at least something that could happen that would cause me to strictly prefer A to A prime。

Okay。So like if that's you know， I won't always have weekly dominated actions。

 but if I do have a weekly dominated action， like I really should， you know。

 and I have any uncertainty at all about what other people are going to do。

 like I probably shouldn't play it。Right， like if I'm considering should I play a prime。

 I should like realize once I noticed that I also have this action A that like any situation in which I would have considered playing a prime。

 like I should just play a instead because it'll always do at least as well and sometimes it'll do better。

😊，Okay， so when I'm thinking about what。Other people might do。Well first of all。

 when I'm thinking about what I should do， I probably shouldn't play dominated actions。

And when I'm thinking about what other people might do。

 maybe I should guess if they're paying attention that they're not going to play dominated action。

Okay。The reason is because there are no situations in which I dominated action as a unique best response and。

There are situations in which it's not a best response at all。Okay。So， you know。

 we can talk about for pairs of actions， A and a prime， it might be that A dominates a prime。

Though that you know that doesn't always happen， here's something that's sort of。

 you know even less common， but really makes strategic thinking easier if the game that I'm playing in happens to have this property。

You， I might have some action A。That weekly dominates all of the other actions。

I might have some action A that weekly dominates all of the other actions， which means。

No matter what everyone else does， I know for sure that A is going to be a best response。哎。

If there's never any situation in which any of the other actions are better than a， that's what。

It means that a weekly dominates every other action。

Right so like normally the thing that makes it hard to think about how to behave in a game it's that。

You know I don't know what other people are going to do and what my best response is depends on what other people are going to do so I need sort of you know some kind of theory of mind for what other people are going to do right but if I happen to have a dominant strategy and I don't I don't care what other people are going to do it's sort of clear how I should play if I want to be playing a best response given what other people do it's to play the dominant strategy。

Okay， so having a dominant strategy is a very strong guarantee it's always a best response it's always the best thing I can do given what others do。

And it eliminates the sort of。Need to have some theory of mind for my opponents。

 it eliminates the need for any kind of like counter speculationulation and understanding of what they're going to do if if I just want to concern myself with what I should do that will maximize my own utility。

ok。😊，So。嗯。You know， okay。Generally dominant strategies don't exist。

 you have to be really lucky to be playing in a game where a dominant strategy exists and you know even less frequently will dominant strategies exist for every player in the interaction。

嗯。But， you know， if we sort of buy this philosophical premise from a few slides back that in any stable situation。

 all players should be playing a best response to one another， if we happen to find ourselves，嗯。

In a situation in which every player in the game has a dominant strategy。Okay。

 then it's easy to predict what's going to happen then then there's sort of there's a clear。

Stable solution。And that's when everyone plays their dominant strategy。Okay， if anyone。

 if there's anyone who's not playing a dominant you know their dominant strategy。

 then they're not playing a best response， they're sort of leaving utility to be on the table。

So okay， here's our sort of。First and most restrictive notion of a stable game state of an equilibrium。

Okay， we'll see a bunch of these， this is the most restrictive。

But we will say that an action profile。A choiceice of action for each of the end players。

Is a dominant strategy equilibrium and let me just you know since this is the first example of these we're seeing let me just sort of take note of the type of these objects。

 the kind of objects that could or could not be an equilibrium of some sort is an action profile。

 a vector of action one for each player。Okay， so a particular action profile is a dominant strategy equilibrium。

For a game。If simultaneously for every single one of the players。

 the action they are playing in that profile， AI is a dominant strategy for them。Okay。

Does it make sense？Is it clear what we're talking about here？Okay， so。Prisoners' dilemma。

 which we talked about last time， is probably like the simplest example of a game that has a dominant strategy equilibrium。

So last time I wrote out prisoners' dilemma in terms of， you know。

 like the number of years spent in jail and you wanted to like minimize the number of years spent in jail。

 it's like abstract away the story and forget like years I'm just writing out the same strategic interaction in terms of utility。

Okay so larger numbers are better now you prefer to be in higher utility states and remember how to read a table like this。

 this is how we would write down like a two player game with in this case two strategies for the row player two strategies for the column player and and entry in this matrix corresponds to two numbers the first is the utility for the row player the second is the utility for the column player okay and。

Any game， the any game matrix that has the same best response structure as this one is called a prisoner's dilemma。

 like the story doesn't matter or the specifics of the numbers。Okay， so， you know。

 you can like stare at this thing and like observe that。

Confess is a dominant strategy for both players。Okay。

 what is that what do we have to like check to like verify that confesses a dominant strategy for both players。

 but we have to check that no matter what the other player does，Confess is a best response for me。

 no matter who I am。Okay， so let's think， you know。

I'm deciding whether I should confess or stay silent。

 I don't know whether my opponent is going to confess or stay silent。

 but I can just go through the case analysis。Maybe he's going to confess。

 well I could stay silent and get utility zero or I could confess and get utility one。

 so the best response here is to confess because more utilities is better。

Or maybe he could stay silent， I could stay silent and get utility3 or I could confess and get utility5。

 five is better than three， and so if he plays silent confess is also a best response。

 confesses a best response in both situations right so no matter what he does。

 which means it's a dominant strategy。And the games symmetric so he can go through the same reasoning and you know for him confesses also a dominant strategy。

 both players have。A dominant strategy， and so the game profile， the play profile。

 which in this case there's only two players， so it specifies in action for each of the two players confess。

 confess is a dominant strategy equilibrium of this game。And it is the only stable state。

In the sense that if we find ourselves in one of any one of these four game states and ask。

What happens if we let one of the players change their action so that they are playing a best response to their opponent？

Confess， confessfess is the only one that doesn't have anyone change their action。

Right anywhere else， right if we find ourselves in silent， silent or confess silent or silent。

 confess will。Have one of the players wishing that they could change their action from silent to confess and so these are not stable solution concepts in the way that confesss confess it right if we sort of draw out the play a trajectory here by drawing little arrows between game states。

UmWhere。They sort of correspond to a single player changing their action to a best response。You。

 we did get like a little graph here and。Confess， confessfes would be like a sink of that graph。

 nobody would want to change， and the others would all have outgoing edges。Okay。

 so if we think of play flu， we'll talk about this more later。

 but if we think of play somehow as traversing this graph where people are sort of changing their action when they have an opportunity to do so to improve their action。

You know， like the you know， the flow of where you go would inevitably converge to the dominant strategy equilibrium in this game。

Okay。😊，So this is like the absolute simplest example of a game that has a dominant strategy equilibrium。

Does that？Make sense， everybody。Okay。So like， okay， you know。

 like if we find ourselves in a game that has a dominant strategy equilibrium。

 like that's a pretty plausible prediction， but you know。

If things have to like align just right for everybody to have a dominant strategy so like we shouldn't stop there right like we're not going to be able to make predictions in very many games if if the only thing we know how to predict is dominant strategy。

 equilibriumria， they generally don't exist。Still， right like we can use the idea of dominance to try to say something about what will happen in the game。

Right， like。I might not have a dominant strategy。But I might have some strategies that are dominate tid。

 and maybe I， you know， I shouldn't play those。 and if I think。You're reasonably clever。

 maybe I should think that you're not going to play your dominated strategies。

 which might change what I want to do。And sometimes。After I go through the exercise of。

Eliminating the dominated strategies。For myself saying I'm not going to play those they're dominated and also illuminating your dominated strategies I'm saying you're not going to play those they're dominated and I look at the subgame that results in which I've now removed some actions。

Right under the presumption that you all won't play dominated strategies。

 it might be that in this new subga。Some more stuff has become dominated。

And so I could continue this process and maybe if I'm lucky， this would iterate down to。

A unique prediction。And so we can consider。Sort of an algorithmic process of iteratively eliminating dominated strategies。

And if we're lucky， I mean， this won't always happen， but if we're lucky。

 it might be that this iterated elimination of dominated strategies。

 even when nobody has a dominant strategy nevertheless results in a single surviving play profile。

And we can think about， you know。What that might tell us about that play profile if it's。

A plausible prediction， maybe not always you guys just played guess the guess two third the average the winning。

Guess wasn't zero， but you know， maybe sometimes and maybe we can think about。

Relationships between strategies that survive the iterated elimination of dominated strategies and other sensible solution concepts that we have yet to define。

Okay。So now I need the ability to。Draw on this thing and。My computer。

 the way to do it is to press shift D exactly five times but。Didn't work here so。外咪。Try something。

 which is just to go to this ugly view and。Mannually select。Draw， okay。Okay， so here's an example。

 it's like a two by four day and I want you guys to help me out first。Obsserve that okay。

 so first of all， there's the row player， they've got four actions， ABC and D。

 there's the column player who's got two actions， X and y。

 and we can observe that nobody has a the players don't there's no dominant strategy equilibrium。

Okay， nevertheless， there might be some actions that are dominated can anyone。唱 me。

Some actions that might be dominated。Yeah。Okay， C and D so you're saying C is dominated by D Yeah。

 like why would I replace C like， you know what？By playing D I'd get like four instead of two in one situation or five instead of four。

 so I really shouldn't play C with crosshouse C。ok。And so like the column player probably， you know。

 knowing that I'm a clever fellow knows I'm not going to play C and so you know from everyone's perspective。

 this is the game now。Anything else dominated in this game， yeah？不是。Yes。

Yeah a good point like why would I ever play B like I could get or you know dominated both by D and I guess also by a right like B just sucks I I could get five instead of three or four instead of three。

So I shouldn't play B。Okay， so like everyone knows I won't play B or C。Now at。In the back。Let's say。

 yeah， so now。Y dominates X because， you know， okay， if the row player plays a。

 I don't care you know two is the same as two， but if the row player plays D。

 I could get path four instead of three by playing y instead of x So y dominates x in this new sub game note that。

Yeah， so y dominates x， okay， so I won't play x。And now you know the game is very simple。

 there's only one action for the column player and now the row player you know faces an easy decision if he sort of believes that people won't play all of the strategies that have been eliminated so far。

 you know， he can play D and get payoff five or he can play a and get payoff four。

 five is better than four， so he decides， you know， okay， I'm going to play D can eliminate a。

 which is now weak dominated and we have a unique prediction。Okay。

 so that's sort of a very small example of iterated elimination of dominated strategies。

One more time on a more painful example， okay。Yes。It did not matter。

It did not matter and thinking about the specifics of what you can and cannot do will occupy part of your first problem set。

Okay。U。Second more painful example， so this is just a bigger example and again it's going to have the property that there's no dominant strategy we can't just look at this thing and say okay obviously you know like there's a single action profile that people are going to play but nevertheless we can make progress by iteratively eliminating dominated strategies so can anyone tell me a dominated strategy。

Yeah。好。Okay，D is dominated by which？这么。Let's see two is bigger than one。

Oh no that's that's good that's in the right direction Yeah okay two is bigger than one negative one is bigger than negative30 is bigger than negative one4 is bigger than1 zero is bigger than negative one so indeed yeah I wouldn't want to play D because C is always at least as good and sometimes better so let's get rid of D。

ropriately crossed out okay， how about now what how about for the column player now that we don't have to worry about the role player playing D。

 what might the column player think。好。X， wait， x dominates which one？你。😊。

Let's see so indeed one is bigger than minus one three is bigger than one four is bigger than one one is bigger than zero so assuming that the row player is not going to play d x dominates v note that if we hadn't eliminated V that wouldn't have been the case because four is not bigger than six but reasoning that the row player won't play d。

We now have that x dominates V。So we can eliminate V from consideration。All right， that was。

DoesThe row player have anything they might want to eliminate？Yeah。B dominates E。

 so let's say two is bigger than one two is bigger than minus3 negative one is bigger than negative two and two is bigger than minus1 indeed so why would you play E given the other things we've eliminated you'd always be better off playing B get rid of that。

Now what。That。X dominates W， so let's see one is bigger than zero， three is bigger than two。

 four is bigger than minus1 indeed， why would you play W， you could play x way better。嗯。没会。Yeah。

C dominates a， let's see zero is bigger than negative3，4 is bigger than minus1。

 zero is bigger than minus2， indeed a sucks compared to C， let's get rid of that。

It was getting smaller now， now watch。Yes。X dominance y。

Three is bigger than zero and four is bigger than minus1 indeed。身再 why。

Now it's just a two by two game。Yeah。B dominates C2 is bigger than zero and two is bigger than zero。

 so you would not want to play C。Okay， and now the row player only has one remaining action and so the column player can just decide between path five and path three。

 no reason to play X and get path three when you could get path five so in this sort of bigger example。

We again see that。Although there's， you know， at like sort of the initial round。

 there's no dominant strategy， like we get lucky and when we start iteratively eliminating dominate T strategies。

 we get to a unique prediction。开系。Yes。我认你。Good question， you will think about this on the homework。

Okay， now I'll go back to。Well screen。想你。Nes I'm sharing my screen， so let's go with that。😔。

Oh I really though。

![](img/f475a97a40833d02824bfd191928093c_2.png)

![](img/f475a97a40833d02824bfd191928093c_3.png)

Okay。嗯。啊，O。All right， so so we sort said okay， you know we have these like dominant strategy equiria if they exist were golden but maybe they don't we just saw some examples of games that didn't have dominant dominant strategy equilibriumria。

Okay， well， you know maybe we can just eliminate dominated strategies， of course。

If we had a dominant strategy， equilibrium， iterated elimination of dominated strategies would have at only one iteration。

 eliminated everything except the dominant strategy equilibrium。Okay， so if we're lucky， we get。

By iterated elimination of dominated strategies， we get to a unique prediction and we don't have to worry sometimes this will work even when there's no dominant strategy equilibrium。

And we don't have to worry that we've sort of。Produced two different like predictive theories that conflict with one another because。

Which would be a problem like you know it's which one do we believe？

But so far we haven't like gotten ourselves into that particular kind of trouble because。

If we happen to have a game that has a dominant strategy， equilibrium。

 that will be what is found via iterated elimination of dominated strategies， in fact。

 in just one round。Okay， but like iterative elimination of dominated strategies is not guaranteed to do anything either。

 right like it might be that nothing is dominated in which case like this hasn't like removed anything from consideration。

Next。And nevertheless less asks makes sense to think about and to ask for stable profiles of actions。

Okay。So。We will say that an action profile， again， a choice of action one for each of the end players。

Is a pure strategy Nash equilibrium？If。Simultaneously for every single one of the players。

And simultaneously， for every alternative strategy。

 AI prime that they might consider playing instead of the action AI they really are playing in this action profile。

It should be that deviating to AI Prime from AI is a bad idea for them personally。

It can't make their utility go up。Okay， or equivalently。

It should be an action profile so that simultaneously every single one of the players is best responding to what all of the other players do。

喂。So a dominant strategy equilibrium is。A pure strategy Nash equilibrium。

But you could imagine a pure strategy Nash equilibrium that was not a dominant strategy Nash equilibrium。

 this is asking for something weaker， a dominant strategy is something that is a best response simultaneously to anything your opponent might be doing。

In the Nash equilibrium， every player is playing a best response just to the particular things that their opponents happen to be doing。

ok。Does this make sense？And。You know， again， like it would be。

A bummer for our development of this theory， if different things we were proposing as ways of making predictions in games came up with predictions that were。

In conflict with one another。And so。Here's a claim that you're going to prove on the homework。

If iterated elimination of dominated strategies results in a unique solution。

 it might not it may not， of course， but if it does。

Then that unique solution has got to also be a pure strategy N equilibrium。

So is a more general concept， there might be pure strategy N equilibria that can't be found by itererate elimination of dominated strategies。

 but if。Iterated elimination of dominated strategies produces a unique prediction that prediction will be of pure strategy national equilibrium。

Okay， you'll prove that on the homework。But they might not exist either。Okay。

 so here's an example it's a simple two player game it's called matching pennies think of this as like the minimal example for。

A game that doesn't have a pure strategy national equilibriums basically。You know， two action。

 rock paper scissors。Okay， so。There's the row player me。

 there's the column player you my action set is heads or tails。

 your action set is heads or tails and。We've got opposing goals what I would like is to。

Pick the same action as you to arrange my coin so that the face siding up is the same one you chose。

But that's exactly what you don't want， you want to choose the opposite action for me。Okay。

 so if we both pick heads or we both pick tails， i'm happy and you're not， I get utility one。

 you get utility minus one， on the other hand， if we pick opposite science。

 if I pick tails and you pick heads or if I pick heads and you pick tails， then I'm unhappy。

I get utility minus one and you're happy， you get utility one。So this is what。

We will an example of what we'll study in some more depth later in the class of a zero sum game notes that our utilities here always sum up to zero I have exactly opposite interests to you I want to pick the same action you do you want to pick a different one。

And。Like we're just not going to agree on a pair of pure strategies to play right like we're not going to agree to play headsheads because。

You're going to， if given the opportunity switch to tails。

 we're not going to agree to play heads tails because。I， if given the opportunity。

 I'm going to switch to heads right none of the four action profiles in this game is stable in the sense that we talked about in the sense that defines a Nash equilibrium。

 none of the four action profiles in this game has the property that we're both playing a best response if I'm playing a best response in one of these action profiles。

 like by definition you are not because we have opposite interest。Okay。

 so there's no pure strategy national equilibrium ever in this game。Makes sense。Sometimes there are。

Yes， sometimes okay， so this is sort of one problem with N pure strategy N Glibria they don't always exist okay。

 so sometimes like it tells us nothing about prediction in other times there might be sort of an embarrassment of riches like there might be lots of pure strategy N Gallibria and。

Just predicting that someone's going to play up pure strategy na equilibrium doesn't tell us anything about like or it doesn't tell us exactly at least what they're going to do because there's more than one。

So here is maybe like。Sort of the classic you know two by two anecdote of you know game theory that is supposed to illustrate that there can be more than one na equilibrium you know here's the backstory maybe。

You knowMy wife and I both love classical music， but I like Ba and she loves Krovinsky。

 but like we also kind of like each other so。Yeah， on the weekend like we don't want to go to like separate performances like we want to like coordinate and go to the same one。

 but like all else was being equal， I would want to go to the Ba one and she'd want to go to the Kvinky one。

Okay， so like writing that down in game form， you know， like。If we both go to Ba。

 I'm like super psyched， I get payoff five， she gets payoff one， if we both go to Strinsky。

 she's super psyched， she gets pay off five， I get payoff one。

 and if we like somehow like miscoorinate and go to other you know like we each go to our own performance。

 you know we're both we're both very sad we get pay off zero。Okay。

So which of these states are pure strategy， NSI Blibbriria？Yeah。A个个。Yeah。

 the ones where we go to the type concert， both of them are there's two pure strategy Nsh equilibrium in this game。

Right， so like first of all。You know。The part the two game states where we mis coordinateor those are not。

Pure strategy N equilibriumria in a N equilibrium both players have to be simultaneously playing a best response to what the others are doing and in these game states neither of us are right I could make myself happier by switching to Strinsky where my wife is she could make herself happier by switching to Ba where I am so both players are not playing best responses。

But if we're both going to bar。😡，Okay， like this is my favorite game state。

 so definitely I'm playing a best response。And my wife would like to move to us both going to Strinsky but she doesn't in this model of the game have the power to do that。

 she can only change her own action so she could like unilaterally like leave and like go to Strinsky but that wouldn't make her happier or she'd be there all by herself so it's not a best response like doing that wouldn't be a best response even though she'd prefer to be in this game state。

So like this is a N equilibrium， we're both playing best responses。

 and so is this in which the situations are reversed。😊，The interaction is symmetric。Okay。

 so there can be。No， pure strategy Nash equilibrium in a game。But also， there can be more than one。

Does that makes sense。Claire。And you can sort of think about， you know。

 maybe it's like helpful to think about。The kind of game dynamics I suggested you might visualize by drawing arrows。

 you know we'll eventually think harder about the graph that results， but if you sort of think about。

These four game states as nodes in a graph and we draw。Errows from each game state。

Two other game states that we could reach if one of the players。Unilaterally deviated。

 unilaterally changed their action to play a best response。What would we see。

 we would see that from these diagonal entries， there are two outgoing arrows。

 one up to this game state， the other to this game state。

 because I could deviate to playing going see Ba， which I'd prefer。

 and my wife could deviate to going to see Sriinsky， which she'd prefer。Okay。

 so from these two game states， we'd have pairs about going arrows to the two diagonal game states。

But。These two game states would both be sinks they'd have no outgoingarrows to any state other than themselves。

 so if you think about you know。Initializing play at one of these game states and letting people best respond whenever they have the opportunity to this is some dynamic where play is moving along this graph and I don't you know whether we end up here or here depends on。

Where we start and what the order of play is， I you know。

 we don't have anything strong at the moment to say where we'll end up， but like。For sure。

 this dynamic will end up at one of the sinks of the graph。不清。All right。Everything clear so far。Okay。

 so like we've been。Thinking about this sort of hierarchy of predictions。

We started with dominant strategies and dominant strategy equilibrium。

Pretty good prediction when they exist， they're unique， you can't have two dominant strategies。嗯。😊。

Okay， so like， you know， if we're playing a prisoner's dilemma。

 maybe we know what prediction to make。And then we sort of generalized that we sort of said， okay。

 we can maybe use the same logic。You know like we ran into this problem dominant strategy equi don't always exist so we want to do something more general。

 we talked about iterate a elimination of dominated strategies and of course you know that's only more general。

 it results in a dominant strategy equilibrium it finds one whenever one exists but sometimes as we saw examples of it can find a unique prediction even when there are no dominant strategy equilibrium so it sort of expands the class of problems that we know how to make some kind of prediction about。

Okay。And then we defined a pure strategy Nash equilibrium。Which can。

Exist even more generally when you know there can be games that have pure strategy Nash equilibriumria but for which iterated elimination of dominated strategies does not find them this is an example nobody has any dominated strategies in this game so iterated elimination of dominated strategies will halt immediately having provided no insight at all nevertheless it has pure strategy Nash equilibriumria。

And we claimed。You know， didn't prove you're going to prove it， but we claimed that again。

 this is only a strictly more general kind of prediction in that。

When it happens that iterated elimination of dominated strategies works to give us a unique solution。

 it'll happen that that solution is a pure strategy N equilibriumous。

 we're not getting conflicting predictions。But again， we have this problem of nonex。

Right like that they might not exist and so it doesn't give us any kind of。You know。

 universal way of thinking about what might happen in a game because suppose we have a game where where there are no pure strategy in national equilibriumria。

 what then？Yes。Okay。So you know， the question is can we like generalize this even further in the same style where we sort of want to give？

Think about kinds of predictions that capture the previous kinds of predictions when they exist。

 but also more general things。So just think of a definition。😊，You know。

 for now you don't need to know much about these， we'll think about them in some depth layer in the class。

But a two player game。Is zero sum？If it kind of looks like rock paper scissors or matching pennies。

The two players have exactly opposing interests if for every game state。

My utility for that game state is exactly the negative of your utility for that game state。

It's called zero sum because if we sum up our utilities， they'll sum to zero。😊，And of course， like。

 you know， when we think about， you know， this is something that。You know， just foreshadowing a bit。

 you know， I mentioned these， you know， sort of best response graphs a few times。

It's really only the best response graph that。Matterters in sort of。

Thinking about a strategic interaction， not the like actual numbers themselves。 So like by the way。

 it's not important that。These utilities sum to zero like they could equally well sum to five or sum to 12 or whatever the point is they all sum to the same thing any change in game state that makes things better for me makes things equally worse for you that's a zero sum game。

😊，Okay， so matching pennies is a zero sum game。And this is sort of a class of games that it tends to be sort of like resistant to pure strategy Nash equilibrium because you know。

 why would we agree on playing？You know， to pure strategies， to deterministic strategies。

If the game is not trivial and I've chosen which one to play because it's better for me， you know。

 like because it was worse for you。But we know how to play such games， right。

How would you actually play matching pennies if you had to play it for money？You know。

 I wouldn't want to be predictable right like I want to get the I want to。

Pick the same action as you， but I know you want to pick the opposite action as me。

So if you knew what action I was going to play， if you could you know。

 guess with any advantage over random guessing what action I was going to play if I'm more likely to play heads then you're going to play tails and that's going to be bad for me。

So the way to play matching pennies is to try to be unpredictable， to randomize。

 to uniformly at random pick。Heads or tails it's the same for rock paper scissors， right like。

It sure seems tempting to play rock because rocks are big and they smash things but。Right， right。

 why would you play paper？But like actually like you know。

 playing rock more than a third of the time is a really bad idea in rock paper scissors because it makes you predictable and therefore exploitable right if I play rock more than a third of the time and you know that you should play paper。

And so also in rock paper scissors， the thing to do if I'm playing against something someone clever is to randomize。

And so far， we just don't have a language for thinking about that。Right like， you know。

 pure strategy N equilibriumria correspond it's a label we can attach to an action profile。

 which as we've discussed it so far， just corresponds to like a deterministic choice of action for each player。

Okay， so we're going to need to generalize that if we're going to want to think about games like matching pennies or rock paper scissors。

And so。Okay， you know， an action， this is what's sometimes called a pure strategy。By contrast。

 a mixed strategy。Is a probability distribution over actions。

 it's something I might do if I'm allowed to randomize。

Okay so a mixed strategy is just a some probability distribution over my set of actions。

 which I'll write as you know， Delta AI this is supposed to。

Evoke an image of the probability simplex。But， you know， it's nothing mysterious。

 it's just a set of numbers， one for each action， each of my actions that I can interpret as probabilities。

So they've got to be non negative， it doesn't make sense to play rock with probability minus 2%。

 or it's got to be non negative。And they've got a thumb to one。Okay。

 if I have some way of assigning numbers to actions that are non negative and that sum to one。

 I can interpret those as probabilities and that vector of actions I will call that that vector of probabilities。

Is something I will call a mixed strategy for me， you could have a mixed strategy for you。嗯。Okay。

 so just as we could think of an action profile， which assigns a choice of action to each of the end players。

 I can think of a mixed strategy profile， which is a vector in the Cartesian product。

Of the set of probability distributions over actions， one for each player。

So it is a mixed strategy profile， it is just an assignment。

To each of the N players of a probability distribution over their action。Okay。Now similarly。

 utility functions as we've defined them， right， like what do they do。

 they take as input action profiles and they output numbers。

 how happy we are with those action profiles。So we need to extend that definition to probability distribution。

 what's my utility if I and others are randomizing over our actions。

And we just extend it by taking expectations。Okay， so I can talk about。My utility at a particular。

Profile of mixed strategies where everyone's randomizing over their choice of action。And。

This is just my expected utility。Where。Everyone， what's the expectation over。

 it's the expectation over the experiment where everyone selects according to their own mixed strategy。

 according to their own probability distribution of actions。App peer strategy and action。Okay。

 so if we all have probability distributions over the actions we intend to play like I'm going to play rock paper scissors each with probability one third。

 you really like scissors because they're so sharp so you're going to play scissors two thirds of the time and rock the other one third。

Now I can figure out， you know， given that I know the payoffs for every pure action profile。

 I can figure out what is my expected utility or it's the expected utility when I randomly sample an action you know。

 from this uniform distribution and you sample an action from this two thirds。

 one third distribution。That's some like well defined thing。

And that's how we're going to think about people's utilities when there's randomization。

That is by the way， like not without loss of generality。

 like assuming that people are going to be like expectation maximizers when they're randomness is something。

 you know， I'm making some assumptions about how they think about risk。

Right like you might not really be you know assumptions like this are sometimes called risk neutrality assumptions you just want to maximize expectations you don't care about variance so there are scenarios where it doesn't make sense to model things like this right you know I sort of defended utility functions as being very general when we were talking about pure strategies。

Here， even just in defining things this way I am making some like modeling assumption here。

 that's not always appropriate。People might not care about expectations， they might be risk averse。

But about let's think about things this way for now。Okay， so does this make sense？

So we can think about randomness randomness now we now have a language。

In order a language to describe strategies that people might play in games that involve flipping coins right that involve randomizing like in rock paper scissors。

And so we can extend our。Collection of solution concepts that sort of。

Are all trying to get at the same idea that。In stable situations。

 everyone should be best responding to what their opponents are doing。

We can extend that to mixed strategies。Okay， so like rock paper scissors。

 it has no pure strategy Nash equilibriumria right like rock scissors like no。

 not a stable situation。But。We can now define。A mixed strategy national equilibrium。Okay。

 what is it Well， the kind of object that a mixed strategy na equilibrium is is a。Vectctor。

 a profile of mixed strategies。1。Mix strategy one， distribution over actions for each of the end players。

We now know how to talk about utility for each player at a mixed strategy profile。

 it's just their expected utility when actions are sampled from their mixed strategies independently。

And。You know， extending our definition in a natural way。We will say that。

A collection of mixed strategies is a mixed strategy Nash equilibrium。If。Simultaneously。

 this should say I not one if simultaneously everyone is playing a best response within the set of mixed strategies now that no matter what。

Action I might consider deviating to instead of playing my mixed strategy PI。

 maybe I consider playing some action AI instead。It's not a good idea， it'll only lower my utility。

 won't raise it。It sort of like an asymmetry and this the way I've written things here。

 you might wonder why am I considering only deviations from playing some mixed strategy PI to playing a pure strategy AI。

 why would I only consider deviations to you know playing a pure strategy。

I could have equivalently written， look， there should be no other mix strategy that would allow me to improve my utility。

But I want to highlight one sort of。Structural observation that's going to be useful to understand。

 which is that。It might be that for strategic reasons at equilibrium we need to randomize like in rock paper scissors the only stable states is that we're going to play rock paper and scissors sort of with uniform probability。

But if I view my opponent as fixed， if I think of what everyone else is doing as fixed and I think to myself what is the thing that I could do that would maximize my utility。

 what is my best response？I always have a best response that is a pure strategy。

 I don't need to randomize to just best respond。Right， like and what's the reason for that？

what is my utility for playing on mixed strategy， it's just my expected utility。

 you know it's my average utility averaged by the probabilities that I put on each of my actions of my utility for playing each of those actions against what my opponents are going to play。

And an average can never be larger than the largest number that you're averaging。

Right so I always have a best response that is a pure strategy。

Like if you tell me you are going to play rock a third of the time paper， a third of the time。

 scissors a third of the time， then rock。And paper and scissors are each。Themselves。

 best responses for me。Right like if you're going to like if you're not going to change what you're doing。

 you're just going to uniformly randomly play rock paper or scissors。

 I will do as well as I can just by playing rock deterministically。

The only reason it's a bad idea to play rock deterministically is because you might change what you're doing to exploit that。

 but if you are fixed， I might as well just play rock。And so here。When we're sort of saying， okay。

 fixing what everyone else is doing， I can't improve my payoff by playing any other pure strategy。

That in particular implies that I can't improve my path by playing any other mixed strategy。Okay。

 so a mixed strategy National equilibriumria is just a set of mixed strategies。

 a set of probability distributions， one for each player so that everyone is simultaneously playing a best response to what everyone else is doing。

But now in this world where we've expanded our notion of what a strategy is to allow randomness。

Does that make sense？And the reason these things are called Nsh equilibriumria Oh， first of all。

 like once again， we're only。Generalizing the set of things we're calling stable stakes a special case。

Of a mixed strategy， a equilibrium is a pure strategy a equilibrium。

RightLike you know just playing rock 100% of the time that is a probability distribution over my actions。

 it's not a very interesting one， but it is a probability distribution。

 I play rock with probability one， I play scissors with probability zero。

 I play paper with probability zero。So a pure strategy Nash equilibrium is in particular a mixed strategy Nash equilibrium。

 this is only a larger set of objects。But there's more now， right， like matching pennies。

 rock paper scissors， they don't have。Pure strategy N equilibrium。

 but they do have mixed strategy in N equilibrium。And the reason these are called mixed strategy。

 the reason these are called Nash equiria is because what John Nash proved in his PhD thesis。

 he might have seen a movie about is that。😊，It's not just these examples of games we've seen。

 but in fact in every single。Game that has a finite number of players isn a finite action set and these caveats about finiteness are important and that you're going to explore on the homework what happens when。

They're not necessarily finite， but if the game is finite。

It is guaranteed to have a mixed strategy Nash equilibrium。Okay， so this is finally。

 we've starting from dominant strategy equilibrium and expanding outwards。

We've gotten ourselves to a solution concept， a notion of stability in which everyone's best responding to everyone else。

That at least in finite games is guaranteed to exist。Okay， it's they might be hard to find。

 there might be more than one of them， but at least we don't have this problem that they don't exist。

Yeah。Okay。And that's going to be the starting point， our starting point in this class。

So the proof it's a fixed point argument， it's non constructive and so。You know， like。They exist。

 but how do you get there you know， that's a question we're going to concern ourselves with for the first bit of this class like you know。

 okay， like， you know， these Nsh equilibriumria they're they're predictions， they're non evauous。

 they like always exist but like they're not necessarily computationally plausible。😊。

So like one of the first questions we're going to investigate over the first you know。

 maybe section of this class is。When they are computationally plausible。

 like when are there stories of game dynamics， we can tell ourselves that will convince ourselves that like reasonable people doing reasonable things will in a reasonable amount of time actually arrive at these stable states。

Okay， so that concludes lecture two。See everybody on。Well， see you guys next class。

 I may have jury duty on Thursday， I'll let you know。不是。嗯。Yeah。



![](img/f475a97a40833d02824bfd191928093c_5.png)