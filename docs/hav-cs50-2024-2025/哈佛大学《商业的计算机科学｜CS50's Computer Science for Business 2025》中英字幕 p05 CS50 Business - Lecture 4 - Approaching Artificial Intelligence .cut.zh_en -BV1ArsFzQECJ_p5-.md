# 哈佛大学《商业的计算机科学｜CS50's Computer Science for Business 2025》中英字幕 p05 CS50 Business - Lecture 4 - Approaching Artificial Intelligence .cut.zh_en -BV1ArsFzQECJ_p5-

![](img/1465a4171d04a32aebba73742fe14c9a_0.png)

Hello world， we are back one more time for a live stream of more artificial intelligence。

 though this is meant to be an overview of artificial intelligence itself again with CS50's own。

 I'm Brian I'll be in the back answering questions via chat please feel free to verbalize them as always feel free to ask them and I will verbalize them as best we can here in the theater this will become part of a course on edx later this year as well stay tuned for more we're off next week but thereafter we hope to be back with all the more live streams for you and we'll follow up by email and socials with those details Brian before we dive into artificial intelligence today among the courses you took in university what was perhaps your favorite that wasn't computer science or linguistics which you also studied Yeah so I studied computer science us。

 a lot of courses I love there a course completely unrelated to that I took a course which was a class on constitutional law taught by professor at the law school which was just totally outside of my comfort zone something completely different from anything Id ever studied before and I really found it quite interesting。

 It's a lot of fun。If we've ever discussed this， like that was my favorite class， but in high school。

 Yeah， I took the college version of that。

![](img/1465a4171d04a32aebba73742fe14c9a_2.png)

Okay， well， all this and more in just a few minutes。😊，Hello world。

 my name is David Main and in this lecture we'll look at the fundamentals of artificial intelligence。

 we'll explore the ideas， strategies and algorithms that， let's fix that。😡，Davi。

 can you look at camera too me？Oh， sorry， I thought we're doing one。Okay，2。You want the screen，Yeah。

 okay。Some of the ideas I say， what's that some of the ideas strategies to make it clear it's not of。

 oh thank you。Overselling you。Ready when you are。Standby which is。Hello world。

 my name is David Main and to this， here we go。😡，Hello world。

 my name is David Main and in this lecture we'll look at the fundamentals of artificial intelligence。

 we'll explore some of the ideas， strategies and algorithms that computer scientists have developed to build intelligent capabilities into computers with CS50's zone。

 Brian Yu。😡，I think that's a keeper， you want to do it once more， so we have it safety。Okay。

They say some of， yep， you did。Ready when you are？在你个。That right。Hello world。

 my name is David Main and in this lecture we'll look at the fundamentals of artificial intelligence。

 we'll explore some of the ideas， strategies and algorithms that computer scientists have developed in order to build intelligent capabilities into computers with CS50's Z。

 Brian Y。😡，喂啊。Yep， first one， slightly better， but whichever。



![](img/1465a4171d04a32aebba73742fe14c9a_4.png)

2。Hi， everyone， I'm Brian。 So as we explore artificial intelligence today and the ideas that make it possible。

 the goal really is to help you understand what artificial intelligence really is， how it works。

 what it's good at and what its limitations are。 So let's start by thinking about what it is that AI does。

 What can we accomplish with artificial intelligence。 Well。

 there are a wide variety of different use cases。 One of the earliest areas where computer scientists were exploring AI was in the world of gameplay of being able to see can we train a computer to be able to play a game well。

 whether it's a simple game liketictk toe or more complex games like chess or go， for example。

 but there are other instances in which AI is started to show up in our everyday lives。 For example。

 handwriting recognition that computers are increasingly able to if you write down a digit or a letter computers can identify what it is that you've written down that are also good at categorizing data in other ways。

 For example， your email inbox。 your computer is automatically classifying some of those emails as spam and others of those emails as not spam and the computer needs to have some process。

 given all of this input。😊，All of the emails that are coming into your computer。

 we need to understand which ones of those we want to classify as spam and how is the computer figuring out how to perform that kind of classification process。

Other potential use cases include things like recommendation systems when you're listening to music online or if you're watching videos or movies。

 for example， you might have watched a whole bunch of videos or movies and a streaming service or a website is going to recommend to you videos that it thinks you might enjoy as well。

 And there needs to be some intelligence there for figuring out how to recommend something to you that you're really going to like。

😊，And other use cases include things like text generation with all sorts of large language models that are available。

 now， we can provide some kind of prompt， some input into a language model。

 something like give me a three day itinerary for a trip to Boston and expect that the computer is going to be able to generate an intelligent reply。

 Give us some good ideas for what we might do on a three day trip to Boston， for example。

 So today we're going to be exploring some of these ideas to get a better understanding for how they work and what the algorithms are that underlie these ideas in artificial intelligence。

 So let's begin with gameplay。 Again， one of the earliest places where computer science research and artificial intelligence begin。

 in part because it offers a bit of a simplified environment for us to start。

 rather than deal with the complexities of the real world where there's so much uncertainty and variables。

 gamess offer a place where there's usually a very fixed set of rules very clear constraints that are easy for computers to work with。

😊，So let's start by imagining a game that you might be familiar with this breakout style video game where you're trying to bounce this ball。

 you're trying to hit these objects up here at the top of the screen。

 And you might imagine what would it take to program a computer to be able to play this game well。

 Well， the computer is going to take some action in response to things that are happening in the game。

 So if we watch the ball， for example， imagine what would happen if the ball moved this way。

 So it moved here。 What action do we want the computer to take。 Well。

 the action we want the computer to take。😊，Is to move the paddle in this case to the left in order to try and catch the ball to make sure we can bounce the ball and make sure it doesn't fall to the bottom of the screen。

 And so we could try imagining encoding that information in a structure that allows us to make decisions by asking questions and telling the computer to make decisions based on the answers to those questions。

 And here's the what we might do to try and get the paddle to move to the left in this particular case。

 we might start by asking a question。The question might be something like。

 is the ball to the left of the paddle。 And depending on whether the answer to that question is yes or no。

 we might make a decision about what to do next。 So if the answer to that question is yes， well。

 then the decision we should make is this。 We should move the paddle to the left。

And if the answer to the question is no， well， then what we should we do。 Well。

 we might say we want to move the paddle to the right。 But actually。

 I think there's a follow up question we might want to ask first。 And that follow up question is。

 is the ball to the right of the paddle。Because if the answer to that is yes， well， then sure。

 we should move the paddle to the right because the ball is to the right of the paddle。

 So we want to move the paddle to the right to try to catch the ball。 But if the answer is no， well。

 then we might say， well now we just don't need to move the paddle at all。

 If the ball is just coming straight down。 For example， it's not to the left or to the right。

 then maybe for now， we don't need to move the paddle until the ball is moving to the left or to the right。

And the advantage of structuring our decision- making process like this。

 asking questions and making decisions based on the answers to those questions is that we can relatively easily convert this idea to code。

 And so I'll show you what that looks like not using a real programming language。

 but using what we call pseudocode， which sort of looks like a programming language。

 but gives you a sense for the logic that we might try to encode in a computer to get it to play this game。

 So the pseudocode might look a little something like this while the game is ongoing。

 repeat this process again and again and the process we're going to repeat。😊。

Is essentially that same decision process we were talking about just a moment ago。

 that if the ball is to the left of the paddle， we'll go ahead and move the paddle to the left。

 Otherwise， if the ball is to the right of the paddle。

 then we're going to move the paddle to the right。 And otherwise。

 if neither of those things are true， we'll go ahead and not move the paddle at all。

 we'll leave it exactly where it is。And we can imagine trying to take the same process of asking questions and making decisions and applying them to other games as well。

 So let's take a different game now， the game oftic ta toe or knots and crosses。

 depending on where you're from。 And the idea oftict toe is that there are two players， X and O。

 you might be familiar with the game。 But if you're not the rules of the game work like this。

 X and O， take turns placing X's and O's in one of the9 cells of this3 by3 grid。

 And the goal for each player is to get3 in a row， either vertically or horizontally or diagonally。

 So x once3 in a row of X's， O， once 3 in a row of O is And we don't mind imagine could be come up with a strategy。

😊。

![](img/1465a4171d04a32aebba73742fe14c9a_6.png)

![](img/1465a4171d04a32aebba73742fe14c9a_7.png)

To get a computer to play this game。 Well， imagine we were playing the game。

 and we were the X player。 We played in the middle and imagine that O responded by playing up here at the top。

 And then we responded by playing here in the corner。

 and O responded by playing in the other corner over there。😊，What is the right move for us to make。

 What action should we take， given this state of the board， Well。

 if the goal is to get three in a row， then I'd say most of us could look at this board and probably determine the right move to make is right here in the lower left corner to be able to get three in a row。

 But what was the process that we used in order to arrive at that conclusion。

 what we asked a question the question we asked was is it possible for me to get three in a row on this turn。

 And if it was， then I played in the spot that allowed me to do that。



![](img/1465a4171d04a32aebba73742fe14c9a_9.png)

That's not always going to be possible， though。 Let's imagine a different board where maybe we started by going in the upper right corner。

 O responded by playing in the middle， and then we responded by playing at the bottom of the board here and O responded by playing on the right here。

 Now， if it's our turn， there's no way for us to immediately get3 in a row。 So what should we do。

 Well， if we're being careful about how we're playing。

 we might notice that O is pretty close to getting three in a row themselves。

 They've got two in a row already。 And so if we don't want O to win on their next turn。

 then we had better block them。 place an X here， for example。😊。



![](img/1465a4171d04a32aebba73742fe14c9a_11.png)

So that idea too， we could encode in the same kind of logic， asking questions and making decisions。

 we might ask can X win on this move， and if the answer to that question is yes。

 we'll then play in the spot that lets us get three x's in a row， we'll win the game。

If that's not true， well then we can ask another question， can O win our opponent。

 Can they win on their next move？And if that's true。

 then we had better play in the spot that blocks them to make sure that they can't get three in a row。

But what if the answer is no， if we can't win on this move and we also can't block our opponent。

 Well， now it gets a little bit more complicated。 It might not be immediately obvious what the right decision to make is。

 And you could probably look at a Tiktk toe board and puzzle it out。 but it's not clear。

 It's not immediately obvious what decision we should make。 But ideally。

 we shouldn't need to be the ones to figure this out if we're trying to get a computer to do this。

 A lot of what artificial intelligence is all about is not just us telling the computer exactly what to do。

 but it's about giving the computer the tools that it needs to figure out on its own what the right decision is。

 And so that's what we'll be looking at here。 is a general algorithm that we can use for gameplay。

 so that we don't need to tell the computer。 exactly what decision to make so that the computer can figure out on its own what the right move is in order to play a game。

And the algorithm we're going to use for gameplay is called miniax。 So how does miniax work。 Well。

 computers ultimately represent things in terms of numbers。

 So if we want a computer to be able to play a game well。

 we're going to need to take this concept of a game。

 This idea of players and actions and turns and winning and losing and turn that into numbers that a computer is going to be able to make sense of。

 So how could we take tickt toe and turn it into numbers。😊，Well， as far as a computer is concerned。

 there are only three outcomes of the game of Tt toe that we really care about。

 We care about one possibility， which is that O wins the game。 One possibility is the game is a tie。

 The whole grid gets filled and nobody's gotten three in a row。

 And one possibility is that X has won the game。 And there are multiple ways that each one of these three outcomes can happen。

 but those are the outcomes that matter at the end， either O wins or X wins or it's a tie。

And what we're going to do is assign a number to each one of those possible outcomes。

 So in this case， we'll say that O winning， we'll call that a negative one value for this game。

X winning will give that a positive one value for the game。 And if it's a tie， nobody's won。

 that we're going to say has a value of 0。

![](img/1465a4171d04a32aebba73742fe14c9a_13.png)

And once we put numbers to each of these possible outcomes。

 now we have the ability to define what the goal for each player is。

 so we might imagine that the X player who we're going to start calling the max player。

 the maximizing player， their goal is to maximize the value of the game。

 They want this blue value to be as high as possible。 one would be best。

 one would mean that X wins the game， but if that's not possible， then0， which means it's the tie。

 that's still better than negative one， which means that O has won the game and therefore X is lost。

😡，Meanwhile， the O player， they have the opposite goal。

 they're who we're going to call the min or minimizing player。

 Their goal is to minimize the game value。 They want the game value to be negative one。

 which means O wins the game。 But if that's not possible。

 then tying the game is still better than X winning the game， for example。

 So both players have a goal。 X wants the game value to be as high as possible。

 One means x wins O wantss the game value to be as low as possible。 So negative one， for example。

 is better than 0 is better than one。😊。

![](img/1465a4171d04a32aebba73742fe14c9a_15.png)

And so let's imagine how we could use these values like to try and evaluate what moves to make in a game。

 Well， let's start with something simple。 Here is a game board。 The game is over。

 And my question for you is， what is the value of this game， Is it negative 1， Is it 0 or is it  one。

😊，Well， if you look at the board， you can see that x has three in a row。 So x is won the game。

 and therefore， the value of this game is one because one is the value we decided for what the value of the game should be if x is won the game。

But now， let me give you a slightly trickier question。 Here's another game board。 And importantly。

 this game is not yet over。 Let's say it's O's turn。 O gets to make take the next move。

 place an O somewhere， and then x might respond by placing an X somewhere。 Now。

 we still want to ask the same question。 What is the value of this game board。

 And the game is not over。 So we don't know if x is going to win or O is going to win or it's going to be a tie。

 But what we want to figure out what miniax is going to help us figure out is if both players are playing optimally。

 Both players are making the best decisions they can at any given point in time。

 what will the value of the game ultimately end up being。😊，And so how could we figure that out， Well。

 O has two options here。 O could place a move in the upper left。

 or O could play in the bottom middle， and miniax will consider both of those options because we need to consider all of our possible moves to decide which move is the best move。

So we'll consider both options。 either O could play in the upper left or O could play in the bottom middle here。

 and we'll explore what will happen in each of those cases。 if O plays in the upper left。

 what will that lead to where there's only one outcome， one choice for X。

 X is going to play in the bottom middle。 X will get three in a row。 X wins the game。

 and that we decided how a value of one。And well， if this game state leads directly to this game state。

 there's no other options， Then this game state must also therefore have a value of one。

 because this means that X is going to win if we ever get to this state。Well。

 what about this game state over here on the right。

 the other option for O was to play in the bottom middle。Then what will X do， X only has one choice。

 which is to play in the upper left corner here。In this game state， nobody has won the game。

 the games over all the cells have been filled in。😡，But nobody won。 It's a tie。

 that has a value of 0。 And so therefore， the game state that leads to it also has a value of 0。

 And so now we have a choice for the O player way back at that original state that we were considering。

 O has two options。 One leads to a value of one。 Another leads to a value of 0。

 And remember that the O player is the minimizing player。

 They want the score to be as low as possible， which means ideally。

 they want the score to be negative one， but that's not possible in this case。

 What they do have is a choice between a value of one and a value of 0。😊。

And so we'll choose the smaller option。 We'll choose to play in the bottom middle。

 which is probably what you would have done too， to try to block X from getting3 in a row。

 And this game state also has a value of 0， meaning if both players are playing optimally。

 they're both making the best moves。 And the end result of the game is that it's going to be a tie。

And we did this in a position that was two moves away from the end of the game。

 But you could have done this at any point in the game as well。

 Just always considering what are all of my possible moves for each of those possible moves。

 What is my opponent's best response to that move， for each of those。

 What is my best response to that move， so on and so forth。

 essentially calculating all of the possible ways the game could go and then making a decision based on which one has the highest value。

 If you're the X player or which one has the lowest value if you're the O player。😊。



![](img/1465a4171d04a32aebba73742fe14c9a_17.png)

And so this miniax algorithm can be used to optimally play a game of Tik To toe。

 If you use this algorithm， you will never lose a game of Tik Tok toe。

 regardless of which player you are。 You'll always be playing the best moves every time。

And we can imagine what would happen if you tried to take this approach and apply it to other games as well。

 Tt toe is a relatively simple game， but imagine a much more complex game， a game like chess。

 where there are more pieces， more squares on the grid。

 more different possibilities for what could happen。 Could you use miniax for a game like chess。😡。



![](img/1465a4171d04a32aebba73742fe14c9a_19.png)

And it turns out you could。 We could imply exactly the same process。

 which is to say you could imagine all of your possible moves and imagine your opponent's best responses to those moves and just ultimately do that calculation to figure out what the right move is。

 And while that would work in theory， in practice， the challenge we're going to run into。

 is there just so many more possibilities for how the game of ches can go。

 that it's going to be difficult for us to be able to calculate all of them。

 I'll show you what I mean。😊，For just the first move in a game of Tktk toe。

 if one player takes a turn in a game of Ttk toe， there are 9 choices for how the first player can take that turn。

 because there are 9 squares on the board。 So there are 9 possibilities for that first turn in Tit toe in chess。

 even if you don't know the rules of chess。 you know that you've got many pieces each of which has different options for how they might move It turns out that there are 20 different options for the first move in a game of chess。

😊，So what about then after the second turn in a game of Ttk toe。

 Well the O player is going to take a turn， they have eight options for what can happen。

 So 9 times 8， that's going to give us 72 possibilities for how a game of Tiktkto can go after two turns。

And what about in a game of chess。 Well， the white player had 20 options for their first move。

 And then the player with the black pieces also has 20 options for their turn as well。

 And so that's going to mean that after  two turns，1 turn by white and  one turn by black。

 That's going to lead to 400 possibilities after just two turns。

 And those possibilities are just going to continue to compound exponentially。

 as we add more and more turns， after  three turns there are about 500 possibilities in Tiktk toe。

 almost 9000 in a game of chess， after  four turns， we're comparing about 3000 with like 200000。

 And you can see after 5 turns after 6，7，8 and then 9 turns。 The game of Tikt toe is over。

 And there are about 260000 possibilities。 The game of chess may have only just started。😊。

And we're looking at something like 2。4 trillion possibilities。

 with still many more turns to be played out in the remainder of the game。

And while 260000 looks like a large number in practice。

 a fast computer nowadays can get through those 260000 possibilities in a matter of seconds。

 It will be very quick for a computer to be able to explore all of the possible games of Tt toe to figure out what the best move is。

 whereas in a game of chess， there are just so many possibilities that even if you gave the computer as much time as you can imagine。

 it's still not going to be enough time to explore all of the possible games of chess to be able to identify what the best move is。

 And so we're going to need some kind of other strategy to be able to figure out how to do that。😊。

Take a short water break and I'll pick up from there。

So what can we do if we still want to be able to train a computer to be able to play chess well。

 Well， the challenge was exploring it to the end of the game of chess just has way too many possibilities。

 The possibilities grow exponentially。 They grow really quickly every time you consider one turn after another turn after another。

 And so one possible choice we can make is to say。We can take a depth limited approach。

 That is to say， don't explore the entire chess game all the way to the end of the game before making a decision。

 We'll only look a certain number of turns ahead。 Maybe we'll look five turns ahead or six turns ahead or seven turns ahead。

 for example。And so what does that look like， Well， if you imagine any given state of the game。

 here's a state of the game of chess。We're going to represent that state of the game using this circular node here。

 oftentimes in computer science， if we're trying to represent relationships between a bunch of different pieces of information。

 we'll put them in a data structure with individual units that we call a node。

 And so this node here represents a state of the game of chess。

 And you could imagine drawing a diagram that connects that state with all of the possible actions that we could choose from for one player's turn and then all of the possible responses to those moves and all of the possible responses to that and so on and so forth for the rest of the game。

 and a game of chess might go on for hundreds of turns potentially。😊。

But in a depth limited miniax approach， what we'll do is we'll say we'll only look a certain number of turns ahead。

 And at that point， we're just going to stop and essentially say we're not going to look any further than that。

 And that's going to allow us to limit the number of possibilities that we need to explore。

 So in computer science and artificial intelligence， often。

 even though we could find the best solution via a brute force approach。

 just trying all of the possibilities。 We need to consider not just making a good decision but making a good decision efficiently in a way that we're actually able to have enough time to make that decision。

 And sometimes that means figuring out what the right tradeoffs are to be able to say。

 looking ahead so many more moves ahead。 we can sacrifice that to be able to make a decision in a realistic time frame for what move we actually want to make in this game of chess。

😊，And so。U。Yeah， okay， I wasn't going to go into detail about。

I should at least mention evaluation functions， even though I don't want to go into detail about it。

 So I'll pick up from there， and。Talk on one more topic before going to the next slide。

So what do we need to change about this algorithm as we're using a depth limited approach now， Well。

 before when we played Tiktke out to the end of the game， we got to the end of the game。

 and then we could just evaluate who won the game， did X win did O win。

 Was it a tie and use that to assign a value to the state of the game in chess。

 if we're doing using a depth limited approach。 if we're only going to look 5 or 6 or 7 or 8 or 9 or 10 turns ahead。

 we might not have reached the end of the game， we don't yet know who is one And so we need to make some prediction as to what we think the state of the game is going to be。

 who we think the winner of the game is going to end up being。

 whether we think the white player is doing better or the player with the black pieces is doing better。

 We need to make some kind of decision there。 And so often what we'll use for that is something called an evaluation function。

 What is an evaluation function。 Well， a function in computer science in this context。

 is just something that can take in some data as input。

 the code can process that input and then produce something as output。

 You might be familiar with mathematical functions that take a number as input and produce a number as output。

😊，In this context in computer science， our evaluation function is going to take one of these states of the game as input and output a prediction for what we think the value of that game is going to be and there are different approaches for how we can construct that evaluation function。

 maybe you'll look at things that like how many pieces the player with the white pieces has versus how many pieces the player with the black pieces has and use that to make a decision maybe you'll look at the particular positions of those pieces and there are also ways that we might be able to train a computer to be able to estimate what we think the evaluation of a particular game state is too。

 but that is going to help us make a decision as to which of these states we think is better than some other states to allow us to make a decision as to what the right move is to make in any particular game。

And so this might be similar to how you might imagine learning to play a game and learning to get good at a game that you get good at a game by if I gave you the rules of a game like the rules of Titto。

 you could sit down with the rules and look at a grid and figure out what you think you want your strategy to be。

 But another way that we get good at things is by learning that you try something you experience it from that experience。

 you learn if you do something well， you learn to do more of that in the future。

 if you do something poorly， you learn to do less of that in the future and you learn from your mistakes to。

 And so one idea we might have is to encode that same possibility for computers as well to allow computers to learn from experience。

 And the idea of computers learning is this general area called machine learning。

 but more specifically what we're interested in here is a form of machine learning called reinforcement learning and reinforcement learning is all about computers learning from experience。

 you start with a computer that's not good at performing some task。

 and through experience the computer gets better at performing that task。

 And so I'll give you a simplified example for。😊。

![](img/1465a4171d04a32aebba73742fe14c9a_21.png)

Might look like。Imagine that we have this grid， this maze that we want a computer to be able to navigate。

 and some of the cells in this grid are walls that we don't want the computer to crash into。

 So we are this sort of computerized AI duck down here in the lower left corner of the screen。

 We're trying to get to this blue star over here。 That's our goal。

 And we need to avoid crashing into the walls。 But imagine initially that our agent。

 our AI agent here， doesn't really know how to navigate about this world。

 It doesn't know where the walls are。 It doesn't know what action to take depending on what square it happens to be in。

 but it needs to somehow find its way to the goal。 Well， how is it going to do that。

If it starts out with no knowledge about anything， it doesn't know what direction to go in。

 It doesn't know where the walls are， the best it could do is to try something at random。

 And maybe we try to go to the right， and we find that we crash into one of the walls， for example。

So that didn't turn out so well。 We go back to the beginning。 but we can learn from that experience。

 The computer can learn that next time you're in this state， you shouldn't go to the right。

 that that is not a direction you should go in because it didn't work out last time。

 it LED to you crashing， it didn't lead to you accomplishing your goal。

 And so next time we learned to try something different。 We learn maybe to go up instead。

 And now we're in a new state when we have' an experience before。

 So we might try something at random， we might try going to the right。 And now again。

 we're in a new state， we might try something random because we don't yet know what to do。

 maybe we try going down and we find we crash into another wall。

 And so now we've learned from that as well。 We've learned that next time we're in this state。

 we better not go down because that didn't lead to good options the last time and we can repeat that process。

 The trial and error。 every time we fail and crashing to something。 we learn from that experience。

 we learn not to do that again。 And that's gonna to keep happening because ultimately。

 we're not really good at this task to begin with。 We keep making it a little bit further， maybe。

 but we're still gonna to end up crashing and we're gonna learn from that mistake。😊。

learn not to do that in the future。 And if you repeat this process for long enough。

 constantly learning from your mistakes and adjusting your behavior accordingly， eventually。

 our agent might end up finding。Some way to navigate about this grid and ultimately end up at the goal。

And once we've achieved that goal， once we've been able to do something that worked out。

 we're able to learn from that too。 We're not just learning from our mistakes。

 We're learning from our successes as well。 So once we've achieved the goal。

 then in future iterations of this computer running。

 we can say we know that we found a sequence of actions that works out really well and we can just follow that sequence of actions to say we know it worked out well last time will follow that same sequence of actions and that ultimately is going to lead us back to the goal because we knew it worked last time。

 too。😊。

![](img/1465a4171d04a32aebba73742fe14c9a_23.png)

And so this is one of the ideas behind reinforcement learning， learning from our mistakes。

 but also learning from our successes。 The one thing you might have noticed is that although we did find a way to get to the goal。

We didn't find the fastest way that， in fact， there was a faster way。

 if we cared about finding a faster way that rather than going down and around this wall over here。

 we could have gone straight up， for example， and that would have LED us to the goal faster。

 But we're not going to be able to find that now because now we've found this path that works。

 and we've trained ourselves to say， once we've found something that works。

 we're going to learn from that。We're going to learn to do more of that。

 And so often in these reinforcement learning， like scenarios。

 we have to balance between two competing priorities。

 And we call these priorities exploring and exploiting。 On one hand。

 we want to exploit our existing knowledge。 If we know that there is a sequence of actions that works。

 then we want to try and use that knowledge to follow it because we know that that leads to good outcomes。

 But on the other hand。😊，We also sometimes want to explore new states。

 new actions that we haven't necessarily tried before。

 because maybe they'll lead to something even better。

 and computers need to balance between these priorities when they're learning to do something new。

And you and I engage in this process of exploring and exploiting every day too。

 you might imagine that if there's like a particular kind of food you like or a restaurant you really like and you're trying to decide where to eat today。

 on one hand， you want to exploit your existing knowledge。

 you know that if you go to a place that you already like， you'll probably have a good time there。

 but on the other hand， you might also want to explore。

 try something new because maybe you'll end up liking that better and the right strategy is often not just always doing one or always doing the other。

 but it's a mix of both to sometimes balance between trying new things that might work out and taking advantage of the knowledge that you already have。

And computers can use this idea of reinforcement learning in a wide variety of circumstances。

 not just games， imagine。Recomer systems， for example。

 where a website is recommending movies for you to watch or videos you might like or music you might like。

 How might they do that。Well， one way they could imagine doing that。

Is by trying to give you recommendations and learning from the successes and failures。

 and what does success and failure look like in this case。

 it's not about like reaching a star or not crashing into a world。

 It might be about whether you choose to click on or watch a video or movie， for example。

 that if it does recommend you something。Sorry， get some water and then pick up from there。

One possible use case for reinforcement learning are recommendation systems。

 systems that are recommending music you might like or videos or movies that you might enjoy watching。

 And how might those work。 Well， these are websites that are maybe giving you videos to watch and you've watched a whole bunch of videos and they're now recommending videos that they think you might like。

 And how might they learn from experience。 Well， the experience in this case is not like whether you reach the star or whether you crashed into a wall。

 it might be whether you chose to click on a video that was recommended to you or not that if a website recommends a video to you and you do choose to click on it and you do watch it either in part or in fold。

😊，Then the website can learn from that success。 It was able to recommend something successfully to you based on the things you would watch before。

😊，It recommended something new。 And it can learn to recommend more of that kind of thing to you in the future。

 And on the flip side， if they recommend a video to and you choose not to watch it or you start watching it。

 and then you immediately stop after a couple of seconds because you realize it wasn't what you wanted。

 Well， then the recommendation system can learn from that failure too。 It can learn that all right。

 I recommended the video that you probably didn't like as much。

 And so maybe I'll recommend fewer of those kinds of things to you in the future。

 So learning from its own experience in order to make the system better at producing results that you might want。

 So reinforcement learning is a wide variety of different possible applications。

 And it's one area where we can see that artificial intelligence can learn from in this case。

 its experience by experiencing things by trying things out and experimenting。

 you can start with an algorithm that's not very good at playing a game。

 not very good at navigating a maze， not very good at making recommendations but through trial and error。

 by learning from feedback。 It's ultimately able to get better at solving these kinds of problems。😊。

Now， what other tools are available to us in this world of artificial intelligence and machine learning。

 One of the most popular is the idea of a neural network。

 And we see neural networks come up all the time in artificial intelligence。

 So let's take a moment and really think about what it is that neural networks are and what it is that they do。

Well， neural networks are inspired by the human brain that the human brain consists of neurons that look a little something like this。

 and they're connected to each other and they pass electrical signal from one to another that if one neuron gets enough electrical signal。

 it can activate or fire and that can trigger another the electrical signal to pass on to another neuron and so on and so forth through a chain of these neurons that might be connected to each other as well。

 And so one idea， just like we were inspired by the way humans learn to come up with the idea of reinforcement learning。

 we might also be inspired by the structure of the human brain to imagine what would it take to take a neural network and make an artificial one。

 a computerized neural network。😊，And what does that look like， Well， instead of biological neurons。

 we have artificial neurons， which you can think of as just a unit like this。

 And this unit is going to store some value。 It's going to store some number。

 kind of like how a neuron in a biological sense， Store some kind of electrical energy。

 And these neurons are going to be connected to each other via these connection。

 So just as neurons can pass electrical signal from one to the other。

 these biological neurons or units of our neural network are going to be able to pass their values from one to the other。

😊，So what is a neural network actually doing， What is it calculating。 Well。

 you can think of a neural network as essentially acting like a function。

 And remember that a function takes an input and produces some kind of output。 And in this case。

 our neural network is going to take in input that is going to be two values。

 And we'll see later that neural networks can take in as input many more than that。 But for now。

 we have a neural network that takes in two values as input。

 and it's going to try and produce one value as output。

 And what the neural network is going to learn to do is it's going to learn how to transform these inputs into that output for almost any task we might imagine trying to predict。

 And so there's a variety of things you might imagine trying to predict。

 maybe you work in a business and you want to predict what your sales are going to be。

 And so you have input data data like the amount of money that you spend on advertising， for example。

 And you want to predict what your sales are going to be based on the input。

 which is the amount of money you spend on advertising。

 Maybe you're trying to predict the weather you're trying to predict whether or not it's going to rain And so this output。

😊。

![](img/1465a4171d04a32aebba73742fe14c9a_25.png)

Here represents， is it going to rain or not， is it a rainy day or not rainy day。

 And your inputs are pieces of data that might contribute to determining whether it's going to rain。

 things like the humidity outside or the pressure， for example。

 our values that might be inputs into the neural network。 Now。

 if you just created a neural network like this and told it to predict I it going to rain or not based on the humidity and pressure。

 initially， the neural network would have no way of knowing what the right answer is。

 we would have no way of knowing what the right decision to make would be。

 And so what we do with the neural network is train it with data。

 that if you gave the computer data of a whole bunch of days in history。

 And we told the computer on each one of those days， here is the humidity， here is the pressure。

 and this is whether or not it rained。 then what the computer can learn to do via this neural network architecture is learn how to compute that output。

 whether or not it rained based on the inputs， meaning in this case， the humidity and the pressure。

 and we're going to learn how to perform that computation。😊，Based on a whole bunch of training data。

 So what does that math actually look like， What math is actually being performed by the neural network。

Well， each one of these inputs we can assign a value to， we'll call this one X。

 we'll call that one y， for example。And then what the neural network is learning are a bunch of parameters。

 Paraas are the specific values that the computer is learning to work with。

 We're going to learn one parameter， which we'll call a that's associated with this first input。

 We'll learn another parameter B， which is associated with the second input。😊。

And we'll also learn a third parameter C that's just not associated with any input。

 That's just general information about whether we think it's likely， in this case。

 maybe that it's going to rain or not rain， for example。

 And so what is the neural network calculating， What the neural network is really going to calculate。

Is it's going to try and combine data from X and Y to predict whether this output belongs to one category or another category。

 like raining or not raining。 for example， And the math that it's going to do is it's going to multiply each of the inputs by its corresponding parameter。

 otherwise known as a weight。 So we multiply a by X。And we multiply B by y。 We add those together。

 And then we also have this additional parameter C that's often called a bias。

 That one's not associated with either one of these inputs。 We're just gonna add that on at the end。

 And then。We just perform a comparison。 We say， is this value at least 0， If it's at least 0。

 we categorize it as one category， like raining。 If it's less than 0。

 then we categorize it as the other category， like not raining。And， of course。

 depending on the values of A， B and C， that's going to determine what kind of output we get for any particular input。

 And that's what a neural network is learning。 When we talk about a neural network of learning to do something machine learning。

 what we really mean is the computer is learning what numbers to use for A。

 B and C that allows this equation to do a good job of predicting some kind of prediction task that we've given to the computer。

Soll give a simple example， imagine that we were going to plot these x and y values on a graph like an x axis and a y axis。

 And imagine I wanted to learn to separate the blue points from the red points。



![](img/1465a4171d04a32aebba73742fe14c9a_27.png)

So I have one category blue， another category red， you could imagine that as like rainy days and not rainy days。

 for example， or any other kind of categorization you might want to do。And initially。

 when you create the neural network， these values， A， B and C， they're going to start out randomly。

 We have no idea what the values should be。 We'll pick random values them。 And as a result。

 they're not going to do a very good job。Of separating the blue dots from the red dots。

 It's kind of a random line here。 And there's one blue dot here。 There's another blue dot there。

 It's not really separating them very well。 But what we're going to do as we add data。

Is we can learn from each additional data point。 we can try and predict。

 given an additional data point， we can make adjustments to that line by adjusting the values of A。

 B and C in order to make it more accurate for the data that we've been given。

 and that's one of the reasons why companies that are trying to build machine learning models care so much about having more and more data。

 because the more data you have， the more you can refine what it is these neural networks that are learning to be able to do a better and better job of trying to make predictions。

So as we add another data point， for example， we might learn that， all right， right now。

 we classified it the wrong way based on the line that we've predicted。

 We predicted red was on this side of the line。 when really。

 it should have been on the other side of the line。 So we learn how to adjust that line。

 how to make changes in in order to make it more accurate。 And every time。😊。

We get a new piece of data。 If we classify it wrong。

 we learn what adjustments we should make to the line to allow it to do a better job of classifying in the future。

 And it's unlikely that in practice， the data will be this clean。 If you have more and more data。

 it's gonna be messy。 You're not gonna to classify things perfectly every single time。

 But usually you can learn to do a pretty good job of trying to distinguish between two different categories by this neural network training process。

😊，So that's what a neural network with two inputs might look like。

 But as we try to deal with more and more complex data， often。

 this representation is going to start to look a little bit more complicated。 For example。

 imagine we wanted to solve a problem like handwriting recognition。 for instance。

 Here's a handwritten digit that's just in a 4 by4 grid of pixels。

 And you might imagine that the way that a computer represents visual information is via pixels that have a certain brightness or not。

 For now， I'm just using white and black and shades of gray in practice。

 you might also have color pixels as well。😊，But each one of these pixels we can for now。

 really just represent as a value， describing how light or dark that pixel is， where 0。99。

 that's a very bright pixel，0。16。 That's a very dark pixel。

 How could a computer learn to classify this digit as the digit 4， for example， Well。

 what we have here。A 16 numbers。 And so one way you could imagine doing this is constructing a neural network that has not two inputs。

 but 16 inputs， one for each one of these possible pixel values and what we want the computer to try and predict is not one category like is it a rainy day or not。

 But maybe if we're trying to classify digits，10 different categories， I it a 0， a 1， a2， a 3。

 a 4 or5，67，8 or 9。 And so we might imagine having 10 outputs for the neural network。

 one for each of the different possible categories that we're trying to categorize a digit as And then draw connections in between them。

And so this neural network， what this is going to learn is it'll have many more parameters than the one we were looking at just a moment ago。

 but it's going to be able to take 16 pixels as input。 this 4 by four grid of pixels。

 that's the input to the neural network。 And what the neural network will learn to do by giving it lots and lots of data that looks like this。

 a bunch of pixels， along with telling the computer。 This is the digit  for。

 you should learn what a4 looks like。 It will then learn to be able to perform these kinds of classifications。

😊，And it turns out， as we add larger and larger data。

 maybe you imagine not just a four by four grade of pixels。

 but a larger grid of pixels we might want to start making modifications to this architecture。

 Oftentimes， neural networks have multiple different layers that are doing multiple kinds of transformations to the data to make it a little bit easier to work with。

 But ultimately， the idea is fundamentally the same what the neural network is doing is it's learning a function。

 a function that is taking as input all of the pixel data and producing an output， a prediction。

 And initially， the neural network starts out not good at doing that， but via training。

 it learns what values to use for all of these many connections you're seeing here to be able to predict that output effectively。

😊，And this is similar for any kind of different classification task that a computer might want to perform。

 We talked earlier about spam email classification that you have an email inbox。

 you get a bunch of email。 The computer classifies some of them as spam。 Some of them is not spam。

 That's also a classification task where the computer takes this input a whole bunch of data And what it's trying to predict is is this a spam email or is it not。

 And you could imagine trying to come up with a neural network for doing that。

 But in order to do that， We need to have some understanding of natural language。

 and we need to get the computer to be able to communicate。😊。

And getting the computer to work with natural language is a little bit complicated because language is inherently ambiguous。

 There are words that have multiple meanings。 There are different ways of saying the same thing。

 And so if we want the computer to understand something like English。

 we're going to need some strategies for figuring out how a computer is really going to be able to do that。

 And one of the first is figuring out how is it that we're going to take words and translate them into numbers。

 because remember that ultimately computers and understand numbers， they're working with numbers。

 And so if we want the computer。😊，To be able to understand language and make sense of words。

 we're going to need some way to translate those words into numbers that can be represented in the computer。

 So how could we do that？ Well， one way would be take every word and give it a number。

 So the word hello， that could be the number one。 And the word cat， that could be the number2。

 The word computer， that could be the number 3， and we could do that for every word in our vocabulary。

 if we have tens of thousands of words， we'd have tens of thousands of numbers。😊。

But it'd be a little bit tricky to work with that because it's difficult to imagine encoding the entire meaning of a word inside just a single number。

 A single number can really just represent one thing。And so often， what we'll do。

 instead of using a single value is we'll use what we call a distributed representation。

 Instead of representing a word with one value， we'll represent the word with multiple values Here。

 I'm representing the word hello with， say， five different numbers。 And in practice。

 it might be more than 5。 I'm just showing five， because it can fit on the screen here。

 But every word。We might associate with a different sequence of numbers。

 a different vector of numbers。 So to speak。 So the word cat that's associated with a different sequence of five values and the word computer。

 that's associated with a different sequence of values as well。

 But that leads to the question of what these numbers actually mean， Like。

 what does it mean for the word computer to be defined using these particular values。And ultimately。

 what they mean is that they have meaning in relation to each other。

 that on its own one particular set of numbers， that doesn't mean much。

 but it does mean something when you compare the meaning of that word with the numbers that we're using to represent the meanings of all of the other words in our vocabulary。



![](img/1465a4171d04a32aebba73742fe14c9a_29.png)

And so you can imagine that if you had like one number。

 you could plot that number on a line in one dimensional space。 If you had two numbers。

 you could plot that number on a grid in two dimensional space，3 numbers， you could plot in 3D space。

 computeruters have no problem thinking in higher dimensions than that。

 even though we might struggle to imagine what if 4 or5 or6 dimensions look like。

 computers can deal with data in multiple dimensions because it's just another number to them。

 And so you can imagine。What would happen if we took all of these representations of numbers。

 which we call embeddings。 and embedding is the numeric representation for the meaning of a word in this context。



![](img/1465a4171d04a32aebba73742fe14c9a_31.png)

And we could imagine plotting all of those meanings of words， all of those embeddings on a graph。

And what we would hope to find the way we're going to try and assign embedding values to words is such that words with a similar meaning end up being located in similar places when we plot their embedding values。

 So when I plot the embedding values。 What I want is for the word for breakfast and the word for lunch。

 Since those two words mean something similar。 they should end up having values that are also kind of similar to each other。

 They numeric values。

![](img/1465a4171d04a32aebba73742fe14c9a_33.png)

![](img/1465a4171d04a32aebba73742fe14c9a_34.png)

Cat and dog。 those are similar words。 And so therefore， they， too。

 should have vector representations， embeddings that are reasonably close to each other。

 Def different from say， breakfast and lunch。 Those words have very different meanings in terms of them。

 And so you can imagine doing that for all of the words that might be in your vocabulary and figuring out where you want to plot each of those words。

So that words with similar meanings end up being in similar locations。 And now。

 how does a computer know that two words have a similar meaning， Well。

 one way they could determine that。

![](img/1465a4171d04a32aebba73742fe14c9a_36.png)

Is based on the context in which a word appears。 The idea will be that if a word shows up in a similar context to other words。

 then odds are， those words have a similar meaning。 For example， if I gave you the words。

For blank she ate。 what word could fill in the blank。Well。

 we could fill it in with a word like breakfast for breakfast she ate is a reasonable way you could fill in that sequence。

 or you could fill it in with the word lunch for lunch she ate is pretty reasonable too。

 as is for dinner she ate。

![](img/1465a4171d04a32aebba73742fe14c9a_38.png)

And so based on that， because the words breakfast， lunch and dinner can all reasonably appear in a similar context。

 we might therefore conclude that the words breakfast。

 lunch and dinner have similar meanings to each other。 And so if you gave a computer， again。

 a large amount of training data， A whole bunch of text。

 the computer could learn what words tend to appear in what context around what other words and use that information。



![](img/1465a4171d04a32aebba73742fe14c9a_40.png)

To figure out what words have similar meanings to each other。

 whereasas a word that didn't fit in in this blank。 For example。

 you probably wouldn't find a lot of example text online that use for Excel。 she ate。 Well。

 that probably tells you。That the word excellent has a very different meaning than words like breakfast and lunch。

One more short break， and I think there's one more topic after this。So using this approach。

 we can assign each word， some embedding， some sequence of values that represents the meaning of that word。

 and then use that as input to something like a neural network that takes us input。

 a sequence of numbers。 And so we could get a neural network to be able to except language as input and process that input and figure out what to do with it。

 to be able to take an email and try and classify it as spam or not spam or potentially even to generate new text on its own too。

 But in order to do that well。😡。

![](img/1465a4171d04a32aebba73742fe14c9a_42.png)

Often， the meaning of a word depends a little bit on the words that appear around it。

 that really knowing what word is going to come next in a sequence。

 If you're trying to generate text the way that online， large language models do， for example。

 it depends on having some kind of understanding， not just of an individual word。

 but how those words relate to each other。 And so what do I mean by that。 Well。

 imagine that we were trying to do something like predict the next word in a sequence。 For example。

 we have a passage like this。 This is a passage from Alice's adventures in Wonderland。

And imagine I ask you to predict what word would come next at the end of this sequence of words。

 What is the next word in the passage。 It's an interesting question because this is exactly what large language models are trying to do when you ask it a question。

 You ask a large language model a question and what it does to try to answer that question is just first predict the first word of the answer。

 and then use that to predict the second word of the answer and then predict the third word of the answer。

 One word at a time， essentially trying to generate what it thinks the likely response is to the question that you've asked。

 if you say， plan me a three- day itinerary for my trip to Boston。

 it's going to figure out one word at a time or strictly speaking one token at a time。

 what's going to come next in that sequence to generate for you your itinerary。

And so what we're asking you to do here is essentially what a large language model would be trying to do。

 which is to say， given the sequence of text， can you figure out what word comes next， And well。

 how would you do that？ Well， you would probably do that by focusing on particular words in this sequence that are helpful for trying to make that prediction。

 For example， the word that immediately precedes the word we're interested in is golden。

 So odds are the next word is something that can be golden。

 And there are other words in this passage that are probably helpful to you here， too。In fact。

 that there was something she tried。 So it's something you could try using， for example。

 earlier in the passage。 we can see that there was a door involved。

 So something she's trying to use with a door earlier in the passage。

 we can see that there are some locks。 And so something with a door and related to locks。

 and then earlier even in the passage。 We see that there's another reference to the word golden。

 And what was that describing， it was describing a key。

 And so all of those clues might allow you to reach the correct conclusion that the next word in the sequence is the word key。

 And how did you figure that out。 you figured that out by understanding the passage and context。

 and in particular， by paying attention to clues in the passage that allowed you to figure out what the next word is。

 Not every word in this passage was useful to you for making that prediction。

But some of the words were useful to you， and you were able to pay attention to those words to be able to identify what was relevant for making the next prediction and one of the key innovations in natural language processing。

 getting computers to really understand languages like English and other natural languages is this idea of building attention into our computer models too that there have been a variety of different architectures for how to get computers is to process natural language。

 one of the most popular nowadays as a type of architecture called the transformer architecture and the transformer architecture is built upon this idea of attention that in order to predict the next word in the sequence。

 what we want to do is allow the meanings of words to be updated based on the other words that appeared in the sequence by paying attention to the words that are particularly relevant。

😊。

![](img/1465a4171d04a32aebba73742fe14c9a_44.png)

And so how does that work， Well， given a sequence of words。

 something like she tried the little golden， for example。

 to take that pious passage from Alice's adventures in Wonderland。

 what a transformer architecture will try to do is look at the sequence and for the word that we're trying to predict like we're trying to predict the next word。

 we'll figure out and calculate what words should we be paying attention to and will'll essentially calculate an attention score for each one of the words that came before it in order to figure out what do I need to pay attention to to increase my likelihood of predicting the next word。



![](img/1465a4171d04a32aebba73742fe14c9a_46.png)

And so when you give a transformer architecture， a large language model。

 a whole bunch of training data， what is it the computer is actually learning。

 What it's learning to do is how to do this attention process。

 how to figure out what words to pay attention to in order to give it the best chance of predicting the next word。

 and we can train it much like we trained our other neural networks that when we predict a word。

 if we get that word right， we learn from that， if we predict a word and we get it wrong。

 then we need to figure out how do we need to adjust the weights。

 adjust the parameters of our neural network to get it to do a better job。😊。



![](img/1465a4171d04a32aebba73742fe14c9a_48.png)

![](img/1465a4171d04a32aebba73742fe14c9a_49.png)

Of performing these kinds of tasks in the future。And so we've now seen a wide variety of different possible approaches for how we can go about artificial intelligence。

 different algorithms that we can use them，  different ways of trying to engage in machine learning。

 we can learn from data that we provide to the computer as training data。

 we can learn from experience， learn through reinforcement by trial and error， try something。

 if it succeeds， we learn to do more of it。 If it fails。 we learn to do less of it。

 And all of these are a variety of different strategies and ideas and algorithms that we can use in order to build intelligent capabilities into computers。

 So I hope you enjoy this exploration of artificial intelligence。 That's it for today。

 and we'll see you next time。😊。

![](img/1465a4171d04a32aebba73742fe14c9a_51.png)

![](img/1465a4171d04a32aebba73742fe14c9a_52.png)

How you like back up。So these are just some of the ideas and strategies and algorithms that computer sciences have。

Sorry。So these are just some of the ideas and strategies and algorithms that computer scientists have developed to figure out how to build these kind of intelligent capabilities into our computers。

 So I hope you enjoyed this exploration of artificial intelligence。 That's all for today。

 Thank you all so much。😊。

![](img/1465a4171d04a32aebba73742fe14c9a_54.png)