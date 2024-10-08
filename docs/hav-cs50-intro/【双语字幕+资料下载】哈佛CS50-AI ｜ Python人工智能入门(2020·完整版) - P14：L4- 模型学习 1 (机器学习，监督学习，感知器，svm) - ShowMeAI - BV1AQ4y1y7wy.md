# 【双语字幕+资料下载】哈佛CS50-AI ｜ Python人工智能入门(2020·完整版) - P14：L4- 模型学习 1 (机器学习，监督学习，感知器，svm) - ShowMeAI - BV1AQ4y1y7wy

![](img/d1fa64ba22d78e5e958d31065456ad72_0.png)

[Music]，all right welcome back everyone to an，introduction to artificial intelligence。

with Python now so far in this class，we've used AI to solve a number of。

different problems giving me a，instructions for how to search for a。

solution or how to satisfy certain，constraints in order to find its way。

from some input point to some output，point in order to solve some sort of。

problem today we're going to turn to the，world of learning in particular the idea。

of machine learning which generally，refers to the idea where we are not。

going to give the computer explicit，instructions for how to perform a task。

but rather we are going to give the，computer access to information in the。

form of data or patterns that it can，learn from and let the computer try and。

figure out what those patterns are try，and understand that data to be able to。

perform a task on its own machine，learning comes in a number of different。

forms and it's a very wide field so，today we'll explore some of the。

foundational algorithms and ideas that，are behind a lot of the different areas。

within machine learning and one of the，most popular is the idea of supervised。

machine learning or just supervised，learning and supervised learning is a。

particular type of task it refers to the，task where we give the computer access。

to a data set where that data set，consists of input/output pairs and what。

we would like the computer to do is we，would like our AI to be able to figure。

out some function that map's inputs to，outputs so we have a whole bunch of data。

that generally consists of some kind of，inputs some evidence some information。

the computer will have access to and we，would like the computer based on that。

input information to predict what some，output is going to be and we'll give it。

some data so that the computer can train，its model on to begin to understand how。

it is this information works and how it，is that the inputs and outputs relate to。

each other but ultimately we hope that，our computer will be able to figure out。

some function that given those inputs is，able to get those outputs there are a。

couple of different tasks within，supervised learning the one we'll focus。

on and start with is known as，classification and classification is the。

problem where if I give you a whole，bunch of inputs you need to figure out。

some way to map those inputs into，discrete categories where you can decide。

what those categories are and it's the，job of the computer to predict what。

those categories are going to be so that，might be for example I give you。

information about a banknote like a US，dollar and I'm asking you to predict for，me doesn't blow。

to the category of authentic banknotes，or does it belong to the category of。

counterfeit banknotes you need to，categorize the input and we want to。

train the computer to figure out some，function to be able to do that。

calculation another example might be the，case of whether something we've talked。

about a little bit so far in this class，where we would like to predict on a。

given day you know is it gonna rain on，that day and is it going to be cloudy on。

that day and before we've seen how we，could do this if we really give the。

computer all the exact probabilities for，you know if these are the conditions。

what's the probability of rain，oftentimes we don't have access to that。

information though but what we do have，access to is a whole bunch of data so if。

we wanted to be able to predict，something like is it going to rain or is。

it not going to rain we would give the，computer historical information about。

days when it was raining and days when，it was not raining and ask the computer。

to look for patterns in that data so，what might that data look like well we。

could structure that data in a table，like this this might be what our table。

looks like we are for any particular day，going back，we have information about like that days。

humidity that days air pressure and then，importantly we have a label something or。

the human has said that on this，particular day it was raining or it was。

not raining so you could fill in this，table with a whole bunch of data and。

what makes this what we would call a，supervised learning exercise is that a。

human has gone in and labeled each of，these data points said that on this day。

when these were the values for the，humidity and pressure that day was a。

rainy day and this day was a not rainy，day and what we would like the computer。

to be able to do then is to be able to，figure out given these inputs given like。

the humidity and the pressure can the，computer predict what label should be。

associated with that day does that day，look more like it's going to be a day。

that rains or does it look more like a，day when it's not going to rain put a。

little bit more mathematically you can，think of this as a function that takes。

two inputs the inputs being the data，points that our computer will have。

access to things like humidity and，pressure so we could write a function f。

that takes as input both humidity and，pressure and then the output is going to。

be what category we would ascribe to，these particular input points what label。

we would associate with that input so，we've seen a couple of example data。

points here we're given this value for，humidity and this value for pressure we。

predict is it going to rain or is it not，going to rain and，information that we just gathered from。

the world we measured on various，different days what the humidity and。

pressure were we observed whether or not，we saw rain or no rain on that。

particular day and this function f is，what we would like to approximate now。

the computer and we humans don't really，know exactly how this function f works。

it's probably quite a complex function，so what we're going to do instead is。

attempt to estimate it we would like to，come up with a hypothesis function H。

which is going to try to approximate，what F does we want to come up with some。

function H that will also take the same，inputs and will also produce an output。

rain or no rain and ideally we'd like，these two functions to agree and as much。

as possible so the goal then of the，supervised learning classification tasks。

is going to be to figure out what does，that function H look like how can we。

begin to estimate given all of this，information all of this data what。

category are what label should be，assigned to a particular data point so。

where could you begin doing this well a，reasonable thing to do especially in。

this situation I have two numerical，values is I could try to plot this on。

like a on a graph that has two axes an x，axis and the y axis and in this case。

we're just going to be using two，numerical values as input but these same。

types of ideas scale as you add more and，more inputs as well we'll be plotting。

things in two dimensions but as we soon，see you could add more inputs and just。

imagine things in multiple dimensions，and while we humans have trouble。

conceptualizing anything really beyond，three dimensions at least visually a。

computer has no problem with trying to，imagine things in many many more。

dimensions that for a computer each，dimension is just some separate number。

that it is keeping track of so it，wouldn't be unreasonable for a computer。

to think in ten dimensions or a hundred，dimensions to be able to try to solve a。

problem but for now we've got two inputs，so we'll graph things along two axes in。

x axis which will here representing，humidity and y axis which here。

represents pressure and what we might do，is say let's take all of the days that。

were raining and just try to plot them，on this graph and see where they fall on。

this graph and you know here might be，all of the rainy days where each rainy。

day with one of these blue dots here，that corresponds to a particular value。

for humidity and a particular value for，pressure and then I might do the same。

thing with the days that were not，raining say take all the not rainy days，figure out what。

their values were for each of these two，inputs and go ahead and plot them on。

this graph as well and up here plotted，them in reds the blue here stands for a。

rainy day and red here stands for a not，rainy day and this then is the input。

that my computer has access to all of，this input and what I would like the。

computer to be able to do is to train a，model such that if I'm ever presented。

with a new input that doesn't have a，label associated with it something like。

this white dot here I would like to，predict given those values for each of。

the two inputs should we classify it as，a blue dot a rainy day or should we。

classify it as a red dot and not rainy，day and if you're just looking at this。

picture graphically trying to say all，right this white dot does it look like。

it belongs to the blue category or does，it look like it belongs to the red。

category I think most people would agree，that it probably belongs to the blue。

category and why is that well it looks，like it's close to other blue dots and。

that's not a very formal notion but it's，the notion that will formalize them in。

just a moment because it seems to be，close to like this blue dot here like。

nothing else is closer to it then we，might say that it should be categorized。

as blue it should fall into that，category of I think that day is going to。

be a rainy day based on that input might，not be totally accurate but it's a。

pretty good guess in this type of，algorithm is actually a very popular in。

common machine learning algorithm known，as nearest neighbor classification it's。

an algorithm for solving these，classification type problems and in。

nearest neighbor classification it's，going to perform this algorithm what it。

will do is given an input it will choose，the class of the nearest data point to。

that input by class we just here mean，category like rain or no rain。

counterfeit or not counterfeit and we，choose the category or the class based。

on the nearest data point so given all，that data we just looked at is the。

nearest data point a blue point or is it，a red point and depending on the answer。

to that question we were able to make，some sort of judgment we were able to。

say something like we think it's going，to be blue or we think it's going to be。

red so likewise we could apply this to，other data points that we encounter as。

well if suddenly this data point comes，about well it's nearest data is red so。

we would go ahead and classify this as a，red point not raining things get a。

little bit trickier though when you look，here，and you asked the same sort of question。

should it belong to the category of blue，points the rainy days or should it。

belong to the category of red points，than not rainy days now nearest-neighbor。

classification would say the way you，solve this problem is a look at which。

point its nearest to that point you look，at this nearest point and say it's red。

it's a not rainy day and therefore，according to nearest neighbor。

classification I would say that this，unlabeled point well that should also be。

red it should also be classified as a，not rainy day but your intuition you。

know might think that that's a，reasonable judgment to make that it's。

the closest thing is a not rainy day so，may as well guess that it's not rainy。

day but it's probably also reasonable to，look at the bigger picture of things。

since to say yes it is true that the，nearest point to it was a red point but。

it's surrounded by a whole bunch of，other blue points so looking at the。

bigger picture there's potentially an，argument to be made that this point。

should actually be blue and with only，this data we actually don't know for。

sure we are given some input something，we're trying to predict and we don't。

necessarily know what the output is，going to be so in this case which one is。

correct is difficult to say but，oftentimes considering more than just a。

single neighbor considering multiple，neighbors can sometimes give us a better。

result and so there's a variant on the，nearest neighbor classification。

algorithm that is known as the K nearest，neighbor classification algorithm where。

K is some parameter some number that we，choose for how many neighbors are we。

going to look at so one nearest neighbor，classification is what we saw before。

just pick the one nearest neighbor and，use that category but with K nearest。

neighbor classification where a K might，be three or five or seven to say look at。

the three or five or seven closest，neighbors closest data points to that。

point works a little bit differently，this algorithm will given an input。

choose the most common class out of the，K nearest data points to that input so。

if we look at the five nearest points，and you know three of them say it's。

raining and two of them say it's not，raining we'll go with the three instead。

of the two because each one effectively，gets one vote towards what they believe。

the category ought to be and ultimately，you choose the category that has the。

most votes as a consequence of that so K，nearest neighbor classification fairly。

straightforward one to understand，intuitively you just，look at the neighbors and figure out。

what the answer might be and it turns，out this can work very very well for。

solving a whole variety of different，types of classification problems but not。

every model is going to work under every，situation and so one of the things we'll。

take a look at today especially in the，context of supervised machine learning。

is that there are a number of different，approaches to machine learning a number。

of different algorithms that we can，apply all solving the same type of。

problem all solving some kind of，classification problem where we want to。

take inputs and organize it into，different categories and no one。

algorithm is necessarily always going to，be better than some other algorithm they。

each have their trade-offs and maybe，depending on the data one type of。

algorithm is going to be better suited，to trying to model that information than。

some other algorithm and so this is what，a lot of machine learning research ends。

up being about that when you're trying，to apply machine learning techniques。

you're often looking not just as one，particular algorithm but trying multiple。

different algorithms trying to see what，is going to give you the best results。

for trying to predict some function that，map's inputs to outputs so what then are。

the drawbacks of K nearest neighbor，classification well there are a couple。

one might be that in a naive approach at，least it could be fairly slow to have to。

go through and measure the distance，between a point and every single one of。

these points that exists here now there，are ways of trying to get around that。

there are data structures that can help，to make it more quickly to be able to。

find these neighbors there are also，techniques you can use to try and prune。

some of this data or remove some of the，data points so that you're only left。

with the relevant data points just to，make it a little bit easier but。

ultimately what we might like to do is，come up with another way of trying to do。

this classification and one way of，trying to do the classification was。

looking at like what are the neighboring，points but another way might be to try。

to look at all of the data and see if we，can come up with some like decision。

boundary some boundary that will，separate the rainy days from the not。

rainy days in the case of two dimensions，we can do that by drawing a line for。

example so what we might want to try to，do is just find some line find some。

separator that divides the rainy days，the blue points over here from the not。

rainy days the red points over there，we're now trying a different approach in。

contrast with the nearest neighbor，approach which just looked at local data。

around the input data point that we，cared about now what we're doing is。

trying to use a technique known as，linear regression to find some sort of。

line that will separate the two halves，from each other now sometimes that are。

actually possible to come up with some，line that perfectly separates all the。

rainy days from the not rainy days，realistically though this is probably。

cleaner than many data sets will，actually be oftentimes data is Messier。

there are outliers there's random noise，that happens inside of a particular。

system and what we'd like to do is still，be able to figure out what a line might。

look like so in practice the data will，not always be linearly separable。

we're linearly separable refers to some，data set where I could like draw a line。

just to separate the two halves of it，perfectly instead you might have a。

situation like this where there are some，rainy points that are on this side of。

the line and some not rainy points that，are on that side of the line and there。

may not be a line that perfectly，separates what path of the inputs from。

the other half that perfectly separates，all the rainy days from the not rainy。

days but we can still say that this line，does a pretty good job and we'll try to。

formalize a little bit later what we，mean when we say something like this。

line does a pretty good job of trying to，make that prediction but for now let's。

just say we're looking for a line that，does as good of a job as we can at。

trying to separate one category of，things from another category of things。

so let's now try to formalize this a，little bit more mathematically we want。

to come up with some sort of function，some way we can define this line and our。

inputs are things like humidity and，pressure in this case so our inputs we。

might call x1 is going to be a represent，humidity and x2 is going to represent。

pressure these are our inputs that we，are going to provide to our machine。

learning algorithm and given those，inputs we would like for our model to be。

able to predict some sort of output and，we are going to predict that using our。

hypothesis function which we called H，our hypothesis function is going to take。

as input x1 and x2 humidity and pressure，in this case and you can imagine if we。

didn't just have two inputs we had three，or four or five inputs or more we could。

have this hypothesis function take all，of those as input and we'll see examples。

of that a little bit later as well and，now the question is what does this。

hypothesis function do well it really，point，on one side of the boundary or is it on。

the other side of the boundary and how，do we formalize that boundary well the。

boundary is generally going to be a，linear combination of these input。

variables at least in this particular，case then what we're trying to do when。

we say linear combination is take each，of these inputs and multiply them by。

some number that we're gonna have to，figure out we'll generally call that。

number awaked for how important should，these variables be in trying to。

determine the answer so we'll wait each，of these variables with some weight and。

we might add like a constant to it just，to try and make the function a little。

bit different and the result we just，need to compare like is it greater than。

zero or is it less than zero to say it，doesn't belong on one side of the line。

or the other side of the line and so，what that mathematical expression might。

look like is this we would take each of，my variables X 1 and X 2 multiply them。

by some weight I don't yet know what，that weight is but it's gonna be some。

number weight 1 and weigh - and maybe we，just want to add some other way to it。

because the function might require us to，shift the entire value up or down by a。

certain amount and then we just compare，if we do all this map is a greater than。

or equal to 0 if so we might categorize，that data point as a rainy day and。

otherwise we might say no rain so the，key here then is that this expression is。

how we are going to calculate whether，it's a rainy day or not we're going to。

do a bunch of math where we take each of，the variables multiply them by a weight。

maybe add an extra weight to it see if，the result is greater than or equal to 0。

and using that result of that expression，we're able to determine whether it's。

raining or not raining this expression，here it's in this case going to refer to。

just some line if you were to plot，diagraph eclis it would just be some。

line and what the line actually looks，like depends upon these weights x1 and。

x2 are the inputs but these weights are，really would determine the shape of that。

line the slope of that line and what，that line actually looks like so we then。

would like to figure out what these，weights should be we can choose whatever。

weights we want but we want to choose，weights in such a way that if you pass。

in a rainy days humidity and pressure，then you end up with a result that is。

greater than or equal to 0 and we would，like it such that if we passed into our。

hypothesis function not rainy days in，then the output that we get should be。

not raining so before we get there let's，try and formalize this a little bit more。

mathematically just to get a sense for，how it is that you'll often see this if。

you ever go further into supervised，machine learning and explore this idea。

one thing is that generally for these，categories will sometimes just use the。

names of the category it's like rain and，not rain often mathematically if we're。

trying to do comparisons between these，things it's easier just to deal in the。

world of numbers so we could just say 1，& 0 1 for raining 0 for not raining so。

we do all this math and if the result is，greater than or equal to 0 we'll go。

ahead and say our hypothesis function，outputs one meaning raining and。

otherwise that outputs zero meaning not，raining and oftentimes this type of。

expression will instead express using，vector mathematics and all the vector is。

if you're not familiar with the term is，it refers to a sequence of numerical。

values you could represent that in，Python using like a list of numerical。

values or a tupple with numerical values，and here we have a couple of sequences。

of numerical values one of our vectors，one of our sequences of numerical values。

are all of these individual weights w0，w1 and w2 so we could construct what。

we'll call a weight vector and we'll see，why this is useful in a moment called W。

generally represented using a boldface W，that is just a sequence of these three。

weights weight 0 weight 1 and weight 2，and to be able to calculate based on。

those weights whether we think a day is，raining or not raining we're going to。

multiply each of those weights by one of，our input variables that W to this。

weight is going to be multiplied by，input variable X 2 W 1 is going to be。

multiplied by input variable X 1 and W 0，well it's not being multiplied by。

anything but to make sure the vectors is，the same length and we'll see why that's。

useful in just a second we'll just go，ahead and say W 0 is being multiplied by。

1 because you can multiply by something，by 1 and you end up getting the exact。

same number so in addition to the weight，vector W will also have an input vector。

that we'll call X that has three values，one again because we're just multiplying。

W zero by one eventually and then X 1，and X 2 so here then we've represented。

two distinct vectors that，Durov weights that we need to somehow。

learn the goal of our machine learning，algorithm is to learn what this weight。

vector is supposed to be we could choose，any arbitrary set of numbers and it。

would produce a function that tries to，predict rain or not rain but it probably。

wouldn't be very good what we want to do，is come up with a good choice of these。

weights so that we're able to do the，accurate predictions and then this input。

vector represents a particular input to，the function a data point for which we。

would like to estimate is that day a，rainy day or is that day a not rainy day。

and so that's going to vary just，depending on what input is provided to。

our function what it is that we are，trying to estimate and then to do the。

calculation we want to calculate this，expression here and it turns out that。

expression is what we would call the dot，product of these two vectors the dot。

product of two vectors just means taking，each of the terms and the vectors and。

multiplying them together w0 x 1 w1，multiply it by X 1 w2 multiply it by X 2。

and that's why these vectors need to be，the same length and then we just add all。

of the results together so the dot，product of dot product of W and X our。

weight vector and our input vector，that's just going to be W 0 times 1 or。

just W 0 plus W 1 times X 1 multiplying，these two terms together plus W 2 times。

X 2 multiplying those terms together so，we have our weight vector which we need。

to figure out we need our machine，learning algorithm to figure out what。

the weights should be we have the input，vector representing the data point that。

we're trying to predict a category for，predict a label for and we're able to do。

that calculation by taking this dot，product which you'll often see。

represented in vector form but if you，haven't seen vectors before you can。

think of it as identical to just this，mathematical expression just doing the。

multiplication adding the results，together and then seeing whether the。

result is greater than or equal to 0 or，not this expression here is identical to。

the expression that we're calculating to，see whether or not that answer is。

greater than or equal to 0 in this case，and so for that reason you'll often see。

the hypothesis function written as，something like this a simpler，representation where the hypothesis。

takes as input some input vector X some，humidity and pressure for some day。

we want to predict an output like rain，or no rain or 1 or 0 if we choose to。

represent things numerically and the way，we do that is by taking the dot product。

of the weight and our input if it's，greater than or equal to zero we'll go。

ahead and say the output is 1 otherwise，the output is going to be 0 and this。

hypothesis we say is parameterize by the，weights depending on what weights we。

choose we'll end up getting a different，hypothesis if we choose the weights。

randomly we're probably not going to get，a very good hypothesis function we'll。

get a 1 or a 0 but it's probably not，accurately going to reflect whether we。

think a day is going to be rainy or not，rainy but if we choose the weights right。

we can often do a pretty good job of，trying to estimate whether we think the。

output of the function should be a 1 or，a 0 and so the question then is how to。

figure out what these weights should be，how to be able to tune those parameters。

and there are a number of ways you can，do that one of the most common is known。

as the perceptron learning rule and，we'll see more of this later。

but the idea of the perceptron learning，rule and we're not going to get too deep。

into the mathematics we'll mostly just，introduce it more conceptually is to say。

that given some data point that we would，like to learn from some data point that。

has an input X and an output Y where Y，is like 1 for rain or 0 for not rain。

then we're going to update the weights，and we'll look at the formula in just a。

moment but the big picture idea is that，we can start with random weights but。

then learn from the data like take the，data points one at a time and for each。

one of the data points figure out all，right what parameters do we need to。

change inside of the weights in order to，better match that input point and so。

that is the value of having access to a，lot of data in the supervised machine。

learning algorithm is it you take each，of the data points and maybe look at the。

multiple times and constantly try and，figure out whether you need to shift。

your weights in order to better create，some weight vector that is able to。

correctly or more accurately try to，estimate what the output should be。

whether we think it's going to be，raining or whether we think it's not。

going to be raining so what does that，weight update look like without going。

into too much of the mathematics we're，going to update each of the weights to。

be the result of the original weight，plus some additional expression and to。

understand this expression，why well why is what the actual output。

is and hypothesis of X the input that's，going to be what we thought the input。

was and so I can replace this by saying，like what the actual value was minus。

what our estimate was and based on the，difference between the actual value and。

what our estimate was we might want to，change our hypothesis change the way。

that we do that estimation if the actual，value in the estimate were the same。

thing meaning we were correctly able to，predict what category this data point，belonged to。

well then actual value minus estimate，that's just going to be zero。

which means this whole term on the right，hand side goes to be zero and the weight。

doesn't change wait I where I is like，wait one or wait 2 or wait zero wait I。

just stays at wait I and none of the，weights change if we were able to。

correctly predict what category the，input belong to but if our hypothesis。

didn't correctly predict what category，the input belong to well then maybe then。

we need to make some changes adjust the，weights so that we're better able to。

predict this kind of data point in the，future and what is the way we might do。

that well if the actual value was bigger，than the estimate then and for now we'll。

go ahead and assume that these X's are，positive values then if the actual value。

is bigger than the estimate well that，means we need to increase the weight in。

order to make it such that the output is，bigger and therefore we're more likely。

to get to the right actual value and so，if the actual value is bigger than the。

estimate then actual value minus，estimate that'll be a positive number。

and so you imagine we're just adding，some positive number to the weight just。

to increase it ever so slightly and，likewise the inverse case is true that。

if the actual value was less than the，estimate the actual value was zero but。

we estimated one meaning of it actually，was not raining but we predicted it was。

going to be raining well then we want to，decrease the value of the weight because。

then in that case we want to try and，lower the total value of computing that。

dot product in order to make it less，likely that we would predict that it。

would actually be raining so no need to，get too deep into the mathematics of。

that but the general idea is that every，time we encounter some data point we can。

adjust these weights accordingly to try，and make the weights better line up with。

the actual data that we have access，and you can repeat this process with。

data point after data point until，eventually hopefully your algorithm。

converges to some set of weights that do，a pretty good job of trying to figure。

out whether a day is going to be rainy，or not raining，and just as a final point about this。

particular equation this value alpha，here is generally what we'll call the。

learning rate it's just some parameter，some number we choose for how quickly。

we're actually going to be updating，these weight values so that if alpha is。

bigger then we're gonna update these，weight values by a lot and if alpha is。

smaller then we'll update the weight，values by less and you can choose a。

value of alpha depending on the problem，different values might suit the。

situation better or worse than others so，after all of that after we've done this。

training process of take all this data，and using this learning rule look at all。

the pieces of data and use each piece of，data as an indication to us have do the。

weight stay the same do we increase the，weights do we decrease the weights and。

if so by how much what you end up with，is effectively a threshold function and。

we can look at what the threshold，function looks like like this on the。

x-axis here we have the output of that，function taking the weights taking the。

dot product of it with the input and on，the y-axis we have what the output is。

going to be zero which in this case，represented like not raining and one。

which in this case represented raining，and the way that our hypothesis function。

works is it calculates this value and if，it's greater than zero or greater than。

some threshold value then we declare，that it's a rainy day and otherwise we。

declare that it's a not rainy day and，this then graphically is what that。

function looks like that initially when，the value of this dot product is small。

it's not raining it's not raining it's，not raining but as soon as it crosses。

that threshold we suddenly say okay now，it's raining now it's raining not now。

it's raining and the way to interpret，this kind of representation is that。

anything on this side of the line that，would be the category of data points。

where we say yes it's raining anything，that falls on this side of the line are。

the data points where we would say it's，not raining and again we want to choose。

some value for the weights that results，in a function that does a pretty good。

job of trying to do this estimation but，one tricky thing with this type of hard。

threshold is that it only leaves two，possible outcomes，right we plug in some data as input and。

the output we get is raining or not，raining and there's no room for anywhere。

in between and maybe that's what you，want maybe all you want is given some。

data point you would like to be able to，classify it into one or two or more of。

these various different categories but，it might also be the case that you care。

about knowing how strong that prediction，is for example so if we go back to this。

instance here where we have a rainy days，on this side of the line not rainy days。

on that side of the line and you might，imagine that let's look now at these two。

white data points this data point here，that we would like to predict a label or。

a category form and this data point over，here that we would also like to predict。

a label or a category for it seems，likely that you could pretty confidently。

say that this data point that should be，a rainy day seems close to the other。

rainy days if we're going by the nearest，neighbor strategy and it's on this side。

of the line if we're going by the，strategy of just saying you know which。

side of the line does it fall on by，figuring out what those weights should。

be and if we're using the line strategy，of just which side of the line does it。

fall on which side of this decision，boundary what we'd also say that this。

point here is also a rainy day because，it follows on the side of the line that。

corresponds to rainy days but it's，likely that even in this case we would。

know that we don't feel nearly as，confident about this data point on the。

left as compared to this data point on，the right therefore this one on the。

right we can feel very confident that，yes it's a rainy day and this one you。

know it's pretty close to the line if，we're judging just by distance and so。

you might be less sure but our threshold，function doesn't allow for a notion of。

less sure or more sure about something，it's what we would call a hard threshold。

it's once you've crossed this line then，immediately we say yes this is going to。

be a rainy day and anywhere before it，we're gonna say it's not a rainy day and。

that may not be helpful in a number of，cases one this is not a particularly。

easy function to deal with if you guess，you get deeper into the world and。

machine learning and are trying to do，things like taking derivatives of these。

curves this type of function makes，things challenging but the other。

challenge is that we don't really have，any notion of gradation between things。

we don't have a notion of yes this is a，very strong，only strong belief that it's going to be。

raining as opposed to you know it's，probably more likely than not that it's。

going to be raining but maybe not，totally sure about that either so what。

we can do by taking advantage of a，technique known as logistic regression。

is instead of using this hard threshold，type of function we can use instead a。

logistic function something we might，call a soft threshold and that's going。

to transform this into looking something，a little more like this something that。

more nicely curves and as a result the，possible output values are no longer，just zero and 1：

04 not raining one for，raining but you can actually get any，real numbered value between zero and one。

that if you're way over on this side，then you get a value of zero okay it's。

not gonna be raining and we're pretty，sure about that if you're over on this。

side you get a value of one like yes，we're very sure that it's going to be。

raining but in between you could get，some real numbered value where a value，like 0。

7 might mean you know we think，it's gonna rain it's more probable that。

it's gonna rain than not based on the，data but we're not as confident as some。

of the other data points might be so one，of the advantages of the soft threshold。

is that it allows us to have an output，that could be some real number that。

potentially reflects some sort of，probability the likelihood that we think。

that this particular data point belongs，to that particular category and there。

are some other nice mathematical，properties of that as well so that then。

is two different approaches to trying to，solve this type of classification。

problem one is this nearest neighbor，type of approach where you just take a。

data point and look at the data points，that are nearby to try and estimate what。

category we think it belongs to and the，other approach is the approach of saying。

alright let's just try and use linear，regression and figure out what these。

weights should be adjust the weights in，order to figure out what line or what。

decision boundary is going to best，separate these two categories it turns。

out that another popular approach a very，popular approach if you just have a data。

set and you want to start trying to do，some learning on it is what we call the。

support vector machine we're not going，to go too much into the mathematics of。

the support vector machine but we'll at，least explore it graphically to see what。

it is that it looks like and the idea or，the motivation behind the support vector。

machine is the idea that there are，actually a lot of different，that we could draw a lot of different。

decision boundaries that we could draw，to separate two groups so if for example。

I had the red data points over here and，the blue data points over here one。

possible line I could draw is a line，like this that this line here would。

separate the red points from the blue，points and it does so perfectly all the。

red points are on one side of the line，all the blue points are on the other。

side of the line but this should，probably make you a little bit nervous。

if you come up with a model and the，model comes up with the line that looks。

like this and the reason why I am is，that you worry about how well it's going。

to generalize to other data points that，are not necessarily in the data set that。

we have access to for example if there，was a point that fell like right here。

for example on the right side of the，line well then based on that we might。

want to guess that it is in fact a red，point but it falls on the side of the。

line where instead we would estimate，that it's a blue point instead and so。

based on that this line is probably not，a great choice just because it is so。

close to these various data points we，might instead prefer like a diagonal。

line that just goes diagonally through，the data set like we've seen before but。

there - there's a lot of diagonal lines，that we could draw as well for example I。

could draw this diagonal line here which，also successfully separates all the red。

points from all of the blue points from，the perspective of something like just。

trying to figure out some setting of，weights that allows us to predict the。

correct output this line will predict，the correct output for this particular。

set of data every single time because，the red points are on one side of the。

blue points are on the other but yet，again you should probably be a little。

nervous because this line is so close to，these red points even though we're able。

to correctly predict on the input data，if there was a point that fell you know。

somewhere in this general area our，algorithm this model would say that yeah。

we think it's a blue point when in，actuality it might belong to the red。

category instead just because it looks，like it's close to the other red point。

what we really want to be able to say，given this data how can you generalize。

this as best as possible is to come up，with a line like this that seems like。

the intuitive line to draw and the，reason why it's intuitive is because it。

seems to be as far apart as possible，from the red data and the，so that if we generalize a little bit。

and assume that maybe we have some，points that are different from the input。

but still slightly further away we can，still say that something on this side。

probably read something on that side，probably blue and we can make those。

judgments that way and that is what，support vector machines are designed to。

do they're designed to try and find what，we call the maximum margin separator。

where the maximum margin separator is，just some boundary that maximizes the。



![](img/d1fa64ba22d78e5e958d31065456ad72_2.png)

distance between the groups of points，rather than come up with some boundary，other。

where in the case before we wouldn't，have cared as long as we're categorizing。

the input well that seems all we need to，do the support the support vector。

machine will try and find this maximum，margin separator some way of trying to。

maximize that particular distance and it，does so by finding what we call the。

support vectors which are the vectors，that are closest to the line and trying。

to maximize the distance between the，line and those particular points and it。

works that way in two dimensions it also，works in higher dimensions where we're。

not looking for some line that separates，the two data points but instead looking。

for what we generally call a hyperplane，some decision boundary effectively that。

separates one set of data from the other，set of data and this ability of support。

vector machines to work in higher，dimensions actually has a number of。

other applications as well but one is，that it helpfully deals with cases where。

data may not be linearly separable so we，talked about linear separability before。

this idea that you can take data and，just draw a line or some linear。

combination of the inputs that allows us，to perfectly separate the two sets from。

each other there are some data sets that，are not linearly separable and some word。

even to you would not be able to find a，good line at all，that would try to do that kind of。

separation something like this for，example or if you imagine here are the。

red points and the blue points around it，if you try to find a line that divides。

the red points from the blue points it's，actually going to be difficult it's not。

impossible to do that any line you，choose well if you draw a line here then。

you've ignored all of these blue points，that should actually be blue and not red。

anywhere else you draw a line there's，going to be a lot of error a lot of。

mistakes a lot of what will soon call，loss to that line that you。

a lot of points that you're going to，categorize incorrectly what we really。

want is to be able to find better，decision boundary that may not be just a。

straight line through this，two-dimensional space and what support。

vector machines can do is they can begin，to operate in higher dimensions and be。

able to find some other decision，boundary like the circle in this case。

that actually is able to separate one of，these sets of data from the other set of。

data a lot better so oftentimes in，datasets where the data is not linearly。

separable support vector machines by，working in higher dimensions can。

actually figure out a way to solve that，kind of problem effectively so that then。

three different approaches to trying to，solve these sorts of problems we see。

them support vector machines and we've，seen trying to use linear regression and。

the perceptron learning rule to be able，to figure out how to categorize inputs。

and outputs we see in the nearest，neighbor approach，no one necessarily better than any other。

again it's going to depend on the data，set the information you have access to。

it's going to depend on what the，function looks like that you're。

ultimately trying to predict and this is，where a lot of research and。

experimentation can be involved in，trying to figure out how it is to best。

perform that kind of estimation but，classification is only one of the tasks。

that you might encounter in supervised，machine learning because in。

classification what we're trying to，predict is some discrete category we're。

trying to predict red or blue rain or。