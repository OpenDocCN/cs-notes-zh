# 【双语字幕+资料下载】辛辛那提 MATH1071 ｜ 离散数学(2020·完整版) - P76：L76- Intro to Markov Chains & Transition Diagrams - ShowMeAI - BV1Sq4y1K7tZ

In this video， we're to talk about Markov chains， which is a type of statistical process that's used widely in probability in statistics and has enormous number of applications。

 And to illustrate the idea of a markov chain。 Let me begin with a concrete example。

 I want to imagine some collection of cities。 I've got four cities here。

 and they each have a rail connection。 So not every city has a direct connection， for example。

 city A is only directly connected to city B， but then B is connected to multiple other ones。 Now。

 unfortunately， there's a lot of crime in these cities。

 but we have a superhero who's here for the rescue。 Unfortunately。

 this superhero has some limitations。 First limitation。

 The superhero can only travel down the connections。 They have to take the train。 They can't f。

 And then secondly， this superhero is a little bit of a forgetful one。

 They don't know where they've been in the past。 If they're at any given city and they want to go to the next one。

What they do is they just look at the different trains they can take different connections and they randomly choose between them。

 they don't remember where they've previously been。

 they just know where they are right now and randomly choose where to go in the future so for example if our Marcovi and superhero starts at city A there's only one possibility for where they could go they could go down to city B there's only that one connection。

😡，But now that they're at city B， there's three possible ways they can go back to city A。

 they can go to city C， or in this case they randomly choose between a three and how would they end up as city D now that they're at city D。

 again， they have randomly choose between the two possibilities go back to city B or onward to cityC。

 perhaps that randomly chosen they go back to city B and then on to cityC， who knows what happens？

So this Marovvian superhero is always deciding the next step is just a random choice based on where they currently are。

😡，So that is the idea of a Markov chain let's put up our formal definition。

 a Markov chain is a sequence of events in this case the sequence of events was they were going between different cities。

Such that the probability of where they go in the future。

 the probability of what the next step is going to be， only depends on the present。

 it only depends on where that superhero was at that particular time。

 not where they'd been in the past。😡，And there's all kinds of statistical processes like this。

 a sequence of events that happens over and over and over again， for example。

 every day you can look outside it either cloudy or rainy or sunny。

 and that fact happens over and over and over again。 And every time you have a sequence of events。

 if you're trying to predict the future， you may sometimes only wish to use the knowledge that you have at the present。

 and sometimes you might wish to also use information from the past。

 and that's the difference between a Markov process and a non-markov process。For example。

 let me now show you a nonmark of superheroes。 This is a new superheoe still have to go along the rail connections。

 but this one has a memory。 This one is going to go between the cities in a way to sort of optimize and see all the cities as often as possible So they start city A again the only option to go to city B。

 And then this superhero is not going to bother going back to A because it's a non-markovvian superhero。

 It knows where it's being in the past the past information that are previously being a is available And so it doesn't choose going back to A。

 it chooses going on to C or D， perhaps going to C and now that it's at C it knows that its being at A and B previously so it's not going to go back that direction and so it goes on to D And so the fact that the probabilities for this superhero depend on more than just where it's currently located on more than just the present means that this superhero is a nonmarkovvian superhero Now I'm actually going to improve the diagram that I have a little。

I'm going to separate out each of these connections to make it more clear that there's an arrow leaving an arrow coming back and one of the things I want to do is try to figure out the probability for each of these different arrows so for example。

 imagine I was at city A。😡，There's only one option for me to go。

 the only option from leaving city A is going to city B， so with probability one or 100% probability。

 anyone that started at city A has to end up at city B。😡，However， if now you're at city B。

 there's three different possible connections back up to A or C or D。

And so if those are all equally likely if you're randomly choosing between them。

 each of those have probability one third so of getting a lot of the arrows now let's imagine you happen to be at cityC。

 there's two possible outputs if you randomly choose between them。

 it's a half for each and similarly for D， there's two outputs again and a half for each of those。

 What I've done here is created something called a transition diagram a transition diagram lists all the possible states in this made up example。

 there's A， B， C and D。And then it lists the probability for every connection。

 every arrow that goes between two states， and so this transition diagram sort of encodes all of the information about the movements of our Marovvian superhero Okay let's do a little bit more serious of an example。

 I'm gonna to try and model the stock market Now in any given week。

 the stock market either goes up or down if it goes up。

 we're going to call it a bull market just some fancy ling and if it goes down。

 we call it a bear market。😡，And this market that we're studying。

 if you look at the historical data is one that has been going up more than it's been going down。

 it's one that's been a bull market more than being a bear market。

 and so the historical data says 75% of the time that it's a bull market。

 it's followed up by another bull market and likewise。

 60% of the time it's a bear market so going down the next week it's also going down again it's another bear market。

These data is just totally made up for the purpose of illustrating this example doesn't represent anything realistic。

 Nevertheless， we can try and model this with a markov chain。

 and the first thing I'm going to do is take my two possible states。

 my bowl of my bear and to finish my transition diagram。

 the diagram that shows all the connections I had put in what are all the possible connections。

 I could start as a bear and become another bear I could start as a bull and become another bull。

 I could start as a bear market week and then the next one be a bull market week or vice versa。

 So there's these four different arrows。 and our job to fill out the transition diagram is to label each of these arrows with the appropriate probability。

Let's first imagine that it starts with a bull market， this week is a bull market's going up。

Then the question is， well， what's going to happen in the next week？Well。

 our data said that 75% of the time it's a bull market。

 the next week is going to be a bull market again， so that arrow going from bull market to itself。

Is supposed to have a 75% chance or a 0。75。And if 75% chance is that it becomes a bull market again。

 then the remaining 25% goes to the other arrow， the chance where it goes from a bull market in one week to a bear market in the following week。

Likewise， if we now focus on when it's a bear market in the first week。

 there's a 60% chance that it becomes a bear market again so I can fill in that arrow and if it's a 60% chance that it goes from bear market to bear market。

 the remaining 40% chance goes from bear market to bull market。

So now I've labeled all of the arrows in my transition diagram with a number。

 and so I'm complete with that。Let's actually use this let's use this example to make some predictions about the future for example。

 I could go and ask what happens two weeks from now if I know is for example。

 a bull market this week。😡，I could make the predictions that's the 75 and the 25 for the following week。

 but what about the week after that？To do this， it's actually useful to use a different type of diagram。

 We've been talking about transition diagrams so far。

 but next I'm going to look at something called a tree diagram。

 So I'm saying I know it is a bull market in this particular week so I'm going just put bull market down there。

😊，Then I know that that splits to the next week and two possibilities， 75% Chan's bull market。

 25% chancen's bear market。That is there's two possibilities for the outcome after one week and if that outcome was that it was a bull market。

 that then again is going to split into 75% chance of a bull market two weeks in the future and 25% for it being a bear market。

Alternatively， if one week in the future it was a bear market。

 that would split according to the diagram as 40% chance of bull market and 60% chance of bear market。

And so what I've got on here is this nice little tree diagram that allows me to start with the certainty of being a bull market and then project one in two weeks into the future。

 as you can imagine， you could keep on doing this for three， four or five。

 100 weeks into the future if you wished， it would just be a much more complicated diagram。😡。

So now let's actually answer that question， what is the probability two weeks in the future of it being a bull market？

Well two weeks in the future of being a bull market， there's actually two different pathways。

 it could be bull bull bull or could be bull， bear bull。

 those are two different approaches to ending up with it being a bull market two weeks into the future。

So to compute the probability of being a bull market two weeks into the future。

 I have to add both branches of the tree diagram that end up with it being a bull market So first the yellow is the 75% chance times another 75% chance that's going to be one way it ends up as a bull market and the other approach is the 25% that it turns to a bear in the first week and then followed by that 40% chance it turns back into a bull that's the blue add those together and I get about a 66% chance of it being a bull market in two weeks so let's recap a little bit about what we've learned and what we need to investigate in the future。

We've seen how a Markov process is one in which the probability for the future only depends on where we are at the present。

 it ignores what happened in the past we've seen how we could draw a transition diagram and we've seen how for multiple predictions into the future a tree diagram is useful。

😡，But we're gonna getting a little bit stuck is that if I had to predict long into the future like for example。

100 steps into the future， this tree diagram would get very。

 very cumbersome and so I want a more efficient way to encode and to manipulate the data that's represented in one of these transition diagrams and indeed in the next video on Markov chains。

 we're gonna to see exactly that we're gonna see how we can use matrices and a little bit of linear algebra。

 don't worry I'll introduce the entire idea to you in order to make these types of manipulations significantly easier All right if you have any questions about this video leave them down in the comments below give the video a like for the YouTube algorithm and we'll do some more math in the next video。

