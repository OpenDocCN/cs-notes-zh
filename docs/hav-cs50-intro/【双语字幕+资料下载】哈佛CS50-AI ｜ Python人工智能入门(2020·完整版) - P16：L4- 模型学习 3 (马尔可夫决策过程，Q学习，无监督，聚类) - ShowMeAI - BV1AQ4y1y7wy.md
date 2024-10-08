# 【双语字幕+资料下载】哈佛CS50-AI ｜ Python人工智能入门(2020·完整版) - P16：L4- 模型学习 3 (马尔可夫决策过程，Q学习，无监督，聚类) - ShowMeAI - BV1AQ4y1y7wy

learn what to do in the future and what，not to do so in order to begin to。

formalize this the first thing we need，to do is formalize this notion of what。

we mean about states and actions and，like，and oftentimes we'll formulate this。

world and as what's known as a Markov，decision process similar in spirit to。

Markov chains which you might recall，from before but a Markov decision。

process is a model that we can use for，decision making for an agent trying to。

make decisions in its environment and，it's a model that allows us to represent。

the various different states that an，agent can be in the various different。

actions that they can take and also what，the reward is，for taking one action as opposed to。

another action so what then does it，actually look like well if you recall a，Markov chain from。

for a Markov chain looked a little，something like this where we had a whole。

bunch of these individual states and，each state immediately transitioned to。

another state based on some probability，distribution we saw this in the context。

of the weather before where if it was，sunny we said with some probability。

you'd only be sunny the next day with，some other probability you'll be rainy。

for example but we could also imagine，rain anymore，we just had these states where one state。

leads to another state according to some，probability distribution but in this。

original model there was no agent that，had any control over this process it was。

just entirely probability based where，with some probability we move to this。

next state but maybe it's going to be，some other state with some other。

probability what will now have is the，ability for the agent in this state to。

choose from a set of actions where maybe，instead of just one path forward they。

have three different choices of actions，that each lead up down different paths。

and even this is a bit of an，oversimplification because in each of。

these states you might imagine more，branching points where there are more。

decisions that can be taken as well so，we've extended the Markov chain to say。

that from a state you now have available，action choices and each of those actions。

might be associated with its own，probability distribution of going to。

various different states then in，addition we'll add another extension。

where anytime you move from a state，taking an action going into this other。

state we can associate a reward with，that outcome saying either R is positive。

meaning some positive reward or R as，negative meaning there was some sort of。

punishment and this then is what we'll，consider to be a Markov decision process。

that a Markov decision process has some，initial set of states of states in the。

world that we can be in we have some set，of actions that given a state I can say。

what are the actions that are available，to me in that state and action that I。

can choose from then we have some，transition model the transition model。

before just said that given my current，state what is the probability that I end。

up in that next state or this other，state the transition model now has，effectively two things we're。

conditioning on we're saying given that，I'm in this state and that I take this。

action what's the probability that I end，up in this next state。

now maybe we live in a very determined，mystic world in this Markov decision。

process we're given a state and given an，action we know for sure what next state。

will end up in but maybe there's some，randomness in the world that when you。

take in a state and you take an action，you might not always end up in the exact。

same state there might be some，probabilities involved there as well the。

Markov decision process can handle both，of those possible cases and then finally。

we have a reward function generally，called R that in this case says what is。

the reward for being in this state，taking this action and then getting to s。

prime this next state so I'm in this，original state I take this action I get。

to this next state what is the reward，for doing that process and you can add。

up these rewards every time you take an，action to get the total amount of。

rewards that an agent might get from，interacting in a particular environment。

modeled using this Markov decision，process so what might this actually look，like in practice。

well let's just create a little，simulated world here where I have this。

agent that is just trying to navigate，its way this agent is this yellow dot。

here like a robot in the world trying to，navigate its way through this grid and。

ultimately it's trying to find its way，to the goal and if it gets to the green。

goal then it's going to get some sort of，reward but then we might also have some。

you know red squares that are places，where you get some sort of punishment。

some bad place where we don't want the，Square，then our agent is going to get some sort。

of punishment as a result of that but，the agent originally doesn't know all of。

these details it doesn't know that these，states are associated with punishments。

but maybe it does know that this state，is associated with a reward maybe it。

doesn't but it just needs to sort of，interact with the environment to try and。

figure out what to do and what not to do，so the first thing the agent might do is。

given no additional information if it，doesn't know what the punishments are it。

doesn't know where the rewards are it，just might try and take an action and it。

takes an action and ends up realizing，that it got some sort of punishment and，experience。

well it might learn that when you're in，this state in the future don't take the。

action move to the right that that is a，bad action to take that in the future if。

you ever find yourself back in the state，don't take this action of going to the。

right when you're in this particular，state because that leads to punishment。

that might be the intuition at least and，so you could try，doing other actions you move up alright。

that didn't lead to any immediate，rewards and maybe try something else。

then maybe try something else and，alright now you found that you got。

another punishment and so you learn，something from that experience so the。

next time you do this whole process you，know that if you ever end up in this。

square you shouldn't take the down，action because being in this state and。

taking that action ultimately leads to，some sort of punishment a negative。

reward in other words and this process，repeats that you might imagine just。

letting our agent explore the world，learning over time what states tend to。

correspond with poor actions and，learning over time what states，correspond with poor actions until。

eventually if it tries enough things，randomly it might find that eventually。

when you get to this state if you take，the up action in this state it might。

find that you actually get a reward from，that and what it can learn from that is。

that if you're in this state you should，take the up action because that leads to。

a reward and over time you can also，learn that if you're in this state you。

should take the left action because that，leads to this state that also lets you。

eventually get to the reward so you，begin to learn over time not only which。

actions are good in particular States，but also which actions are bad such that。

once you know with some sequence of good，actions that leads you to some sort of。

reward our agent can just follow those，instructions follow the experience that。

it has learned we didn't tell the agent，what the goal was we didn't tell the。

agent where the punishments were but the，agent can begin to learn from this。

experience and learn to begin to perform，these sorts of tasks better in the。

future and so let's now try to formalize，this idea formalize the idea that we。

would like to be able to learn in this，state taking this action is that a good。

thing or a bad thing there are lots of，different models from reinforcement。

learning we're just going to look at one，of them today and the one that we're。

gonna look at is a method known as cue，learning and what cue learning is all。

about it's about learning a function a，function Q that takes inputs s and a。

where s is a state and a is an action，that you take in that state and what Q。

is this q function is going to do is it，is going to estimate the value how much。

reward will I get from taking this，action in this state originally we don't。

know what this q function should be，but over time based on experience based。

on trying things out and seeing what the，result is I would like to try and learn。

what q of Si is for any particular state，and any particular action that I might。

take in that state so what is the，approach well the approach originally is。

we'll start with Q si equal to zero for，all states s and for all actions a that。

initially before I've ever started，anything before I've had any experiences。

I don't know the value of taking any，action in any given state so I'm going。

to assume that the value is just zero，all across the board but then as I。

interact with the world as I experience，rewards or punishments or maybe I go to。

a cell where I don't get either a reward，or a punishment I want to somehow update。

my estimate of Q si I want to，continually update my estimate of Q si。

based on the experiences and rewards and，punishments that I've received such that。

in the future my knowledge of what，actions are good and what states will be。

better so when we take an action and，receive some sort of reward I want to。

estimate the new value of Q si and I，estimate that based on a couple of，different things。

I estimate it based on the reward that，I'm getting from taking this action and。

getting into the next state but assuming，like the situation isn't over assuming。

there are still future actions that I，might take as well I also need to take。

into account the expected future rewards，that if you imagine an agent interacting。

with the environment and sometimes，you'll take an action and get a reward。

but then you can keep taking more，actions and get more rewards that these。

both are relevant both the current，reward I'm getting from this current。

step and also my future reward and it，might be the case that I'll want to take。

a step that doesn't immediately lead to，a reward because later on down the line。

I know it will lead to more rewards as，well so there's a balancing act between。

current rewards that the agent，experiences and future rewards that the。

agent experiences as well and then we，need to update q si so we estimate the。

value of Q si based on the current，reward and the expected future rewards。

and then we need to update this q，function to take into account this new。

estimate now we already as we go through，this process will already have an。

estimate for what we think the value is，now we have a new estimate and then。

somehow we need to combine these two，estimates together and we'll look at。

more formal ways that we can actually，begin to do that so to actually show you。

what this formula looks like here is the，approach will take with q-learning。

we're going to again start with Q of SN，a being equal to 0 for all states and。

then every time we take an action a in，state s and observe a reward R we're。

going to update our value our estimate，for Q of Si and the idea is that we're。

going to figure out what the new value，estimate is minus what our existing。

value estimate is so we have some，preconceived notion for what the value。

is for taking this action in this state，maybe our expectation is we currently。

think the value is 10 but then we're，going to estimate what we now think it's。

going to be maybe the new value estimate，is something like 20 so there's a delta。

of like 10 that our new value estimate，is 10 points higher than what our。

current value estimate happens to be，here，we need to decide how much we want to。

adjust our current expectation of what，the value is of taking this action in。

this particular state and what that a，difference is how much we add or。

subtract from our existing notion of how，much do we expect the value to be is。

dependent on this parameter alpha also，called the learning rate and alpha。

represents in effect how much we value，new information compared to how much we。

value old information an alpha value of，1 means we really value new information。

but if we have a new estimate then it，doesn't matter what our old estimate is。

we're only going to consider our new，estimate because we always just want to。

can't Kea take into consideration our，new information so the way that works is。

that if you imagine alpha being 1 well，then we're taking the old value of Q si。

and then adding one times the new value，minus the old value and that just leaves。

us with the new value so when alpha is 1，all we take into consideration is what。

our new estimate happens to be but over，time as we go through a lot of。

experiences we already have some，existing information we might have tried。

taking this action nine times already，and now we just tried it a tenth time，and we don't only want。

consider this tent experience I also，want to consider the fact that my prior。

nine experiences those were meaningful，to and that's data I don't necessarily。

want to lose them and so this alpha，controls that decision controls how。

important is the new information zero，would mean ignore all the new。

information just keep this Q value the，same one it means replace the old。

information entirely with the new，information and somewhere in between。

keep some sort of balance between these，two values we can put this equation a。

little bit more formally as well the old，value estimate is our old estimate for。

what the value is of taking this action，in a particular state that's just Q of。

sna so we have it once here and we're，gonna add something to it we're gonna。

add alpha times the new value estimate，minus the old value estimate but the old。

value estimate we just look up by，calling this Q function and what then is。

the new value estimate based on this，experience we have just taken what is。

our new estimate for the value of taking，this action in this particular state。

well it's going to be composed of two，parts it's going to be composed of what。

reward did I just get from taking this，action in this state and then it's going。

to be what can I expect my future，rewards to be from this point forward so。

it's going to be our sum reward I'm，getting right now plus whatever is。

tomato I'm going to get in the future，and how do I estimate what I'm going to。

get in the future well it's a bit of a，another call to this Q function it's。

going to be take the maximum across all，possible actions I could take next and。

say all right of all of these possible，actions I could take which one is going。

to have the highest reward so this then，looks a little bit complicated this is。

going to be our notion for how we're，going to perform this kind of update。

then I have some estimate some old，estimate for what the value is of taking。

this action in the state and I'm going，to update it based on new information。

that I experienced some reward I predict，what my future reward is going to be and。

using that I update what what is tomato，reward will be for taking this action in。

this particular state and there are，other additions you might make to this。

algorithm as well sometimes it might not，be the case that future，you want to wait equally to current。

rewards maybe you want an agent that，values like reward now over a reward。

later and so sometimes you can even add，another term in here some other。

parameter where you discount future，rewards and say future rewards are not。

as valuable as rewards immediately the，getting reward in the current time step。

is better than waiting a year and，getting rewards later but that's。

something up to the programmer to decide，what that parameter ought to be but the。

big picture idea of this entire formula，is to say that every time we experience。

some new reward we take that into，account we update our estimate of how。

good is this action and then in the，future we can make decisions based on。

that algorithm once we have some good，estimate for every state and for every。

action what the value is of taking that，action then we can do something like。

implement a greedy decision-making，policy that if I am in a state and I。

want to know what action should I take，in that state well then I consider for。

all of my possible actions what is the，value of Q si what is my estimated value。

of taking that action in that state and，I will just pick the action that has the。

highest value after I evaluate that，expression so I picked the action that。

has the highest value and based on that，that tells me what action I should take。

at any given state that I'm in i can，just greedily say across all my actions。

this action gives me the highest，expected value and so I'll go ahead and。

choose that action as the action that I，take as well but there is a downside to。

this kind of approach and the downside，comes up in a situation like this where。

we know that you know there is some，solution that gets me to the reward and，out。

but it might not necessarily be the best，way or the fastest way if the agent is。

allowed to explore a little bit more it，might find that it can get the reward。

faster by taking some other route，instead by going through this particular。

path that is a faster way to get to that，ultimate goal and maybe we would like。

for the agent to be able to figure that，out as well but if the agent always。

takes the actions that it knows to be，best well when it gets to this。

particular square it doesn't know that，this is a good action because。

never really tried it but it knows that，going down eventually leads its way to。

this reward so what might learn in the，future that it should just always take。

this route and it's never going to，explore and go along that route instead。

so when reinforcement learning there's，this tension between exploration and。

exploitation and exploitation generally，refers to using knowledge that the AI。

already has the AI already knows that，this is a move that leads to reward so。

we'll go ahead and use that move an，exploration is all about exploring other。

actions that we may not have explored as，thoroughly before because maybe one of。

these actions even if I don't know，anything about it might lead to better。

rewards faster or two more rewards in，the future and so an agent that only。

ever exploits information and never，explores might be able to get reward but。

it might not maximize its forwards，because it doesn't know what other，possibilities are out there。

possibilities that would only know about，by taking advantage of exploration and。

so how can we try and address this well，one possible solution is known as the。

epsilon greedy algorithm where we set，epsilon equal to how often we want to。

just make a random move where，occasionally we will just make a random。

move in order to say let's try to，explore and see what happens and then。

the logic of the algorithm will be with，probability 1 minus Epsilon choose the。

estimated best move in a greedy case，we'd always choose the best move but in。

epsilon greedy were most of the time，going to choose the best movement or。

sometimes going to choose the best move，but sometimes with probability Epsilon。

we're going to choose a random move，instead so every time we're faced with。

the ability to take an action sometimes，we're gonna choose the best move。

sometimes we're just going to choose a，random move so this type of algorithm n。

can be quite powerful in a reinforcement，learning context by not always just。

choosing the best possible move right，now but sometimes especially early on。

allowing yourself to make random moves，that allow you to explore various。

different possible states and actions，more and maybe over time you might。

decrease your value of Epsilon more and，more often choosing the best move after。

you're more confident that you've，explored what all of the possibility is，actually。

so we can put this into practice and one，very common application of reinforcement。

learning is in game playing that if you，want to teach an agent how to play a。

game you just let the agent play the，game a whole bunch and then the reward。

signal happens at the end of the game，when the game is over if our a I won the。

game it gets a reward of like 1 for，example and if it lost the game it gets。

a reward of negative 1 and from that it，begins to learn what actions are good。

and what actions are bad you don't have，to tell the AI what's good and what's。

bad but the AI figures it out based on，that reward winning the game is some。

signal losing the game is some signal，and based on all of that it begins to。

figure out what decisions it should，actually make so one very simple game。

which you may have played before is a，game called NIM and in the game of NIM。

you've got a whole bunch of objects and，a whole bunch of different piles where。

here I've represented each pile as an，individual row so you've got one object。

in the first pile three in the second，pile five in the third pile seven in the。

fourth pile and the game of NIM is a，two-player game where players take turns。

removing objects from piles and the rule，is that on any given turn you were。

allowed to remove as many objects as you，want from any one of these piles any one。

of these rows you have to remove at，least one object but you can remove as。

many as you want from exactly one of the，piles and whoever takes the last object。

loses so player one might like remove，four from this pile here player two。

might remove four from this pile here so，now we've got four piles left one three。

one and three and player one might，remove you know the entirety of the。

second pile player two if they're being，strategic might remove all might remove。

two from the third pile，now we've got three piles left each with。

one object left player one might remove，one from one pile player two removes one。

from the other pile and now player one，is left with choosing this one object。

from the last pile at which point player，one loses the game so fairly simple game。

piles of objects any turn you choose how，many objects to remove from a pile。

whoever removes the last object loses，and this is the type of game you could。

encode into an AI fairly easily because，the states are really just four numbers。

every state is just how many objects in，each of the four piles and。

actions are things like how many am I，going to remove from each one of these。

individual piles and the reward happens，at the end that if you were the player。

that had to remove the last object then，you get some sort of punishment but if。

you were not and the other player had to，remove the last object well then you get。

some sort of reward so we could actually，try and show a demonstration of this。

that I've implemented an AI to play the，game of NIM all right so here what we're。

going to do is create an AI as a result，of training the AI on some number of。

games that the AI is going to play，against itself where the idea is the AI。

will play games against itself learn，from each of those experiences and learn。

what to do in the future and then I the，human will play against the AI so。

initially we'll say train zero times。

![](img/b7a5235e5a53a7df848b73225d711ede_1.png)

meaning we're not gonna let the AI play，any practice games against itself in。

order to learn from its experiences，we're just gonna see how well it plays。

and it looks like there are four piles I，can choose how many I remove from any。

one of the pile ISM so maybe from pile，three I will remove five objects for。

example so now a I chose to take one，item from pile zero so I'm left with。

these piles now for example and so here，I could choose maybe to say I would like。

to remove and from pile two I'll remove，all five of them for example and so AI。

chose to take two away from pile one now，I'm left with one pile that has one。

object one pile that has two objects so，from pile three I will remove two。

objects and now I've left the ayah with，no choice but to take that last one。



![](img/b7a5235e5a53a7df848b73225d711ede_3.png)

until the game is over and I was able to，win but I did so because the AI was。

really just playing randomly it didn't，have any prior experience that it was。

using in order to make these sorts of，judgments now let me let the AI train。

itself on like ten thousand games I'm，gonna let the AI play ten thousand games。

of NIMH against itself every time it，wins or loses it's going to learn from。



![](img/b7a5235e5a53a7df848b73225d711ede_5.png)

that experience and learn in the future，what to do and what not to do so here。

then I'll go ahead and run this again，and now you see the AI running through a。

whole bunch of training games ten，thousand training games against itself。

and now it's going to let me make these，sorts of decisions so now I'm gonna play。

against the AI and maybe I'll remove one，from pile three and the AI took。

everything from pile three so I'm left，with three piles I'll go ahead and from。

pile two maybe remove three items and，the AI removes one item from pile zero。

and left with two piles each of which，has two items in it I'll remove one from。

pile one I guess and the AI took two，from pile two leaving me with no choice，but to take one away。

from pile one so it seems like after，playing 10，000 games of NIMH against。

itself the AI has learned something，about what states and what actions tend。

to be good and has begun to learn some，sort of pattern for how to predict what。

actions are going to be good and what，actions are going to be bad in any given。

state so reinforcement learning can be a，very powerful technique for achieving。

these sorts of game playing agents，agents that are able to play a game well。

just by learning from experience whether，that's playing against other people or。

by playing against itself and learning，from those experiences as well now NIM。

is a bit of an easy game to use，reinforcement learning for because there。

are so few states there are only states，that are as many as how many different。

objects are in each of these various，different piles you might imagine that。

it's going to be harder if you think of，a game like chess or a games where there。

are many many more States and many many，more actions that you can imagine taking。

where it's not going to be as easy to，learn for every state and for every。

action what the value is going to be so，oftentimes in that case we can't。

necessarily learn exactly what the value，is for every state and for every action。

but we can approximate it so much as we，saw with minimax that we could use a。

depth limiting approach to stop，calculating at a certain point in time，we can do a similar type of。

approximation known as function，approximation in a reinforcement，learning context where instead of。

learning a value of Q for every state，and every action we just have some。

function that estimates what the value，is for taking this action in this。

particular state that might be based on，various different features of the state。

that the environment that the agent，happens to be in where you might have to。

choose what those features actually are，but you can begin to learn some patterns。

that generalize beyond one specific，state and one specific action that you。

can begin to learn if certain features，tend to be good things or bad things。

reinforcement learning can allow you，using a very，similar mechanism to generalize beyond。

one particular state and say if this，other state looks kind of like this。

state then maybe the similar types of，actions that worked in one state will。

also work in another state as well and，so this type of approach can be quite。

helpful as you begin to deal with，reinforcement learning that exists in。

larger and larger state spaces where，it's just not feasible to explore all of。

the possible states that could actually，exist so there then are two of the main。

categories of reinforcement learning，supervised learning where you have。

labeled input and output pairs and，reinforcement learning where an agent。

learns from rewards or punishments and，it receives the third major category of。

machine learning that we'll just touch，on briefly is known as unsupervised。

learning and unsupervised learning，happens when we have data without any。

additional feedback without labels that，in the supervised learning case all of。

our data had labels we label the data，point with whether that was a rainy day。

or not rainy day and using those labels，we were able to infer what the pattern，banknote。

and using those labels we were able to，draw inferences and patterns to figure。

out what it does a bank note look like，versus not in unsupervised learning we。

don't have any access to any of those，labels but we still would like to learn。

some of those patterns and one of the，tasks that you might want to perform an。

unsupervised learning is something like，clustering we're clustering it's just a。

task if given some set of objects，organize it into distinct clusters。

groups of objects that are similar to，one another and there's lots of。

applications for clustering it comes up，in genetic research where you might have。

a whole bunch of different genes and you，want to cluster them into similar genes。

if you're trying to analyze across a，population or across species and it。

comes up in an image if you want to take，all the pixels of an image cluster them。

and in different parts of the image，comes a lot a lot up in market research。

if you want to divide your consumers，into different groups so you know which。

groups to target with certain types of，product advertisements for example and a。

number of other contexts as well in，which clustering can be very applicable。

one technique for clustering is an，algorithm known as k-means clustering。

and what k-means clustering is going to，do is it is going to divide all of our。

data points into K different clusters，and it's going to do so by repeating。

this process of assigning points to。

![](img/b7a5235e5a53a7df848b73225d711ede_7.png)

clusters and then moving around those，clusters at centers we're going to。

define a cluster by its center the，middle of the cluster and then assign。

points to that cluster based on which，center is closest to that point and I'll。

show you an example of that now here for，example I have a whole bunch of。

unlabeled data just various data points，that are in some sort of graphical space。

and I would like to group them into，various different clusters but I don't。

know how to do that originally and let's，say I want to put assign like three。

clusters to this group and you have to，choose how many clusters you want in。

k-means clustering that you could try，multiple and see how well those values。

perform but I'll start just by randomly，picking some places to put the Centers。

of those clusters and maybe I have a，blue cluster a red cluster in a green。

cluster and I'm going to start with the，Centers of those clusters just being in。

these three locations here and what，k-means clustering tells us to do is。

once I have the Centers of the clusters，of assign every point to a cluster based。

on which cluster Center it is closest to，so we end up with something like this。

where all of these points are closer to，the blue cluster Center than any other。

cluster Center all of these points here，are closer to the green cluster Center。

than any other cluster Center and then，these two points plus these points over。

here those are all closest to the red，cluster Center instead so here then is。

one possible assignment of all these，points to three different clusters but。

it's not great that it seems like in，this red cluster these points are kind。

of far apart in this green cluster these，points are kind of far apart it might。

not be my ideal choice of how I would，cluster these various different data。

points but k-means clustering is an，iterative process that after I do this。

there's a next step which is that after，I've assigned all of the points to the。

cluster Center that it is nearest to we，are going to recenter the clusters。

meaning take the cluster centers these，diamond shapes here and move them to the。

middle or the average effectively of all，of the points that are in that cluster。

so we'll take this blue point this blue，Center and go ahead and move it to the，middle or to the。

Center of all of the points that were，assigned to the blue cluster moving it。

slightly to the right in this case and，we'll do the same thing for red we'll。

move the cluster Center to the middle of，all of these points weighted by how many。

points there are there are more points，over here so the red centre ends up。

moving a little bit further that way and，likewise for the Green Center there are。

many more points on this plate this side，of the Green Center so the Green Center。

ends up being pulled a little bit，further in this direction so we recenter。

all of the clusters and then we repeat，the process we go ahead and now reassign。

all of the points to the cluster center，that they are now closest to and now。

that we've moved around the cluster，centers these cluster assignments might。

change that this point originally was，closer to the red cluster Center but now。

it's actually closer to the blue cluster，Center same goes for this point as well。

and these three points that were，originally closer to the green cluster。

Center are now closer to the red cluster，Center instead so we can reassign what。

colors are what's which clusters each of，these data points belongs to and then。

repeat the process again moving each of，these cluster means from the middles of。

the cluster ism to the mean the average，of all of the other points that happen。

to be there and repeat the process again，go ahead and assign each of the points。

to the cluster that they are closest to，so once we reach a point where we've。

assigned all the points to clusters to，the cluster that they are nearest to and。

nothing changed we've reached a sort of，equilibrium in this situation where no。

points are changing their allegiance and，as a result we can declare this。

algorithm is now over and we now have，some assignment of each of these points。

into three different clusters and it，looks like we did a pretty good job of。

trying to identify which points are more，similar to one another than they are two。

points in other groups so we have the，green cluster down here this blue。

cluster here and then this red cluster，over there as well and we did so without。

any access to some labels to tell us，what these various different clusters。

were we just used an algorithm in an，unsupervised sense without any of those。

labels to figure out which points belong，to which categories and again lots of。

applications for this type of clustering，technique and there are many more。

algorithms in each of these various，different fields within machine learning，supervised D'Andrea。

foresman and unsupervised but those are，many of the big-picture foundational。

ideas that underlie a lot of these，techniques the word that these are the。

problems that we're trying to solve them，and we try and solve those problems。

using a number of different methods of，trying to take data and learn patterns。

in that data whether that's trying to，find neighboring data points that are。

similar or trying to minimize some sort，of loss function or any number of other。

techniques that allow us to begin to try，to solve these sorts of problems that。

then was a look at some of the，principles that are at the foundation of。

modern machine learning this ability to，take data and learn from that data so。

that the computer can perform a task，even if they haven't explicitly been。

given instructions in order to do so，next time we'll continue this。

conversation about machine learning，looking in other techniques we can use。



![](img/b7a5235e5a53a7df848b73225d711ede_9.png)