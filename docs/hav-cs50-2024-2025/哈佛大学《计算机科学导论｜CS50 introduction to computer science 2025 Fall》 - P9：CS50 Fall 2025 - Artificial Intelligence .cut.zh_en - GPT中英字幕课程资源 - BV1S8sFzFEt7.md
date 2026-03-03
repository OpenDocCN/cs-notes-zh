# 哈佛大学《计算机科学导论｜CS50 introduction to computer science 2025 Fall》 - P9：CS50 Fall 2025 - Artificial Intelligence .cut.zh_en - GPT中英字幕课程资源 - BV1S8sFzFEt7

Alright， this is C S 50， and this is our lecture on artificial intelligence or AI。

 particularly for all of those family members who are here in the audience with us for the first time。

 In fact， for those students among us maybe a round of applause for all of the family members who have come here today to join you。

😊，Rightice。So nice to see everyone。 And as CS50 students already know。

 it's sort of a thing in programming circles to have a rubber duck on your desk。

 Indeed a few weeks back， we gave one to all CS 50 students and the motivation is to have someone something to talk to in the presence of a bug or mistake in your code or confusion you're having when it comes to solving some problem And the idea is that in the absence of having a friend family member T of whom you can ask questions is to literally verbalize your confusion。

 your question to this in object on your desk and in that process of verbalizing your own confusion and explaining yourself quite often does that proverbial light bulb go off over your head。

 Andvoila problem is solved Now as CS50 students also know we sort of virtualize that rubber duck over the past few years and most recently in a form of this guy here So in students programming environment within CS50。

 a tool called visual studio code at a URL of CS50 dev。

 they have a virtual rubber duck available to them at all times。

 and early on in the very first version。😊，This rubber duck。

 it was a chat window that looked like this。 And if students had a question。

 they could simply type into the chat window， something like I'm hoping you can help me solve the problem。

 And for multiple years， all the CS50 duck did was respond with one2 or three quacks we have anecdotal evidence to suggest that that alone was enough for answering students questions because it was in that process of like actually typing out their confusion that you realize I'm doing something silly and you figure it out on your own。

 But of course， now that we live in an age of chatpt and Claude and Gemini and all of these other AIbased tools came as no surprise。

 perhaps when in 2023， this same duck started responding to students in English。

 And that now is the tool that they have available。

 which is in effect meant to be a less helpful version of chat1 that doesn't just spoil answers out。

 but tries to guide them to solutions akin to any good teacher or tutor。

 And so today's lecture is indeed on just that And the underlying building blocks that make possible that their rubber duck and all of the AI with which we' all increasingly familiar。

Nely generative artificial intelligence， using this technology known as AI to generate something。

 whether that's images or sounds or video or text。 And in fact。

 what we thought we'd do to get everyone involved early on is if you have a phone by your side。

 If you'd like to go ahead and scan this Q R O Q R code here And that's gonna lead you to a polling station where you can buzz in with some answers。

 I'm C5 these preceptor Kelly' is going kindly join me here on stage to help run the keyboard and what we're about to do is play a little game and see just how good we humans are right now at distinguishing AI from reality。

 And so we'll borrow some data from the New York Times。

 which a couple years back actually publish some examples of AI and not AI and we'll see just how good this this technology has gotten。

 So here we have two photographs on the screen in a moment， you'll be asked on your phone。

 If you we're successful in scanning that code。 Which one of these is AI left or right。😊。



![](img/24ee856e37b0fd5c7eff7d735daa31d1_1.png)

So hopefully on your phone here， if you want to go ahead and swipe to the next screen。

 we'll activate the poll here。 in a moment you should see on your phone a prompt。😡。

Inviting you to select left。Or right。Feel free to raise your hand if you're not seeing that。

 but it looks like the responses are coming in。 and at the risk of spoiling。

 it looks like 70% plus of you think it is the answer on the right。 And if Kelly。

 maybe we could swipe back to the two photographs in this particular case。 Yes， it was， in fact。

 the one on the right。 Maybe it looked a little too good。 or maybe a little too unreal。 maybe。

 let's see maybe a couple of other examples。 So same Q R code， no need to rescan。

 let's go ahead and pull up these two examples。 Now， two photographs， same question。

 Which of these is AI left or right。😊。

![](img/24ee856e37b0fd5c7eff7d735daa31d1_3.png)

Left。Or right。All right want to take a look at the chart。

 see what the responses are coming in a little closer in this case。

 but a majority of you think the answer is， in fact， left here， though。

5% of you are truthfully admitting that you're unsure。 But Kelly。

 if you want to swipe back to the photos， the answer this time was， in fact， a trick question。

 They were both， in fact， AI， which。Perhaps speaks to just how good this technology is already getting Neither of these faces exists in the real world。

 It was synthesized based on lots of training data。 So two photographs that look like humans。

 but do not in fact， exist。 How about one more this time focusing on text， which will be the focus。

 of course， underlying our duck。 did a fourth grader write this or the new chatbo。

 Here are two final examples。 same code as before。 So no need to rescan。 And here are the texts，1。

 I like to bring a yummy sandwich in a cold juice box for lunch。

 And sometimes I'll even pack a tasty piece of fruit or a bag of crunchy chips。 as we eat。

 we chat and laugh and catch up on each other's day dot dot dot2。 My mother packs me a sandwich。

 A drink fruit and a treat when I get into a lunchroom。

 I find an empty table and sit there and eat my lunch。 My friends come and sit down with me。

 dot dot dot。 The question now， Lastly， is which of these is AI 1 or two。😊。



![](img/24ee856e37b0fd5c7eff7d735daa31d1_5.png)

Ssay one or two。The bars here are duking themselves out。 Looks like a majority of you say S 1。

 Let's go back to the text。 And someone of you who， one of you who says S1， why。

 if you want to raise a quick hand， why S1， yeah。

![](img/24ee856e37b0fd5c7eff7d735daa31d1_7.png)

Okay， and so SA2 looks more like you would write in to kind of ask what grade you are in。😡。

A fifth grader， so is this a new fifth grader or not？The answer here， in fact。

 is that S1 is the AI because indeed S2 is more akin to what a fourth， or if I may。

 a fifth grader would write。 And I dare say there are maybe some telltale signs。

 I'm not sure a typical fourth grader or fifth grader would catch up on each other's day in the vernacular that we see in S1。

 but suffice it to say this game is not something we can play in the years to come。

 because it's just going get too hard to discern something that's AI generated or not。

 And so among our goals for today is really to give you a better sense of not just how technologies like this duck in these games that we've played here with images and text work。

 but really what are the underlying principles of artificial intelligence that frankly have been with us and have been been developing for decades and have really now come to a head in recent years。

 thanks to advances in research thanks to all the more cloud computing thanks to all the more memory and disk space and information。

 sheer volume thereof that we have at our disposal that can be used to train all of these here technologies。

 So that there duck is built on a fairly complicated。😊。

architecturechiitecture that looks a little something like this where here's a student using one of CS50's tools。

 Here's a website with which CS50 students are familiar called CS50 AI。

 where we the staff wrote a bunch of code that actually talks to what are called APIs application programming interfaces。

 Thirdparty services by companies like Microsoft and Open AI that really have been doing the hard work of developing these models as well as some local some local sauce that we sees50 add into the mix to make it specific the duck's answers to CS50 itself。

 But what we've essentially been doing is something with which you might be familiar in part prompt engineering。

 which is started popping up for better or for worse on LinkedIn profiles everywhere and prompt engineering really。

 it's not so much a form of engineering as it is a form of asking good questions and being detailed in your question giving context to the underlying AI so that the answer with high probability is what you want back。

 And so there's two terms in this world of prompt engineering that are worth knowing about So in CS50 has leveraged both of these to implement that duck。

 We， for instance， wrote。What's called a system prompt。

 which are instructions written by us humans often in English that sort of nudge the underlying AI technology to have a certain personality or a specific domain of expertise。

 For instance， we C S 50， have written a system prompt essentially that looks like this。 In reality。

 it's like a lot of lines long nowadays。 But the essence of it is this。

 You are a friendly and supportive teaching assistant for C S 50。You are also a rubber duck。

 And that is sufficient to turn an AI into a rubber duck。 It turns out。

 answer student questions only about C 50 in the field of computer science。

 do not answer questions about unrelated topics， do not provide full answers to problem sets as this would violate academic honesty。

 answer this question， colon。 And after that preamble， if you will， Aka system prompt。

 we effectively copy paste whatever question a student has typed in otherwise known as a user prompt。

 And that is why the duck behaves like a duck in our case and not a cat or a dog or a PhD。

 but rather something that's been attenuated to the particular goals we have pedagogically in the course。

 And in fact， those of you who are C S 50 students might recall from quite some weeks ago in week 0。

 when we first introduced the course to the class。 we had code that we whipped up that day that ultimately looked a little something like this。

 And I'll walk through briefly line by line。 But now on the heels of having studied some python in C 50。

 this here code that I whipped up in the first lecture might make now a bit more sense in that。

 we imported open AI's own library code that a thirdpart company wrote to make it possible for us to implement code on top of theirs。

 We created a variable called client in week0。 And this gave us access to the open AI client that is software that they wrote for us。

 We then defined in week 0， a user prompt， which came from the user using the input function with which the 50 students are now familiar。

 And then we defined this system prompt that day where I said， limit your answer to one sentence。

 Pre you do do do cat。 I think was the persona of the day。

 And then we used some bit more arcane code here。 But in essence。

 we created a variable called response， which was meant to represent the response from openaiI server。

 we used client response create， which is a function or method that open AI gives us that allows us to pass in three arguments。

 the input from the user that is the user prompt the instructions from us that is the system prompt and then the specific model or version of AI that we wanted to use and the last thing we did that day was print out response do output underscore text。

 And that's how we were able to。😊，Questions like what is C 50 or the like。

 So we've seen all of that before。 but we didn't talk about that week exactly how it was working or more we could actually do with it。

 And so in fact， what I thought we do today It peel back a layer that we've not allowed into the course up until now and indeed。

 you still cannot not use this feature until the very end of the class in C 50 when you get to your final projects at which point you are welcome and encouraged to use VS code in this particular way。

 So here again is VS code for those in familiar， this is the programming environment we use here with students。

 and let me open up some code that was assigned to students a couple of weeks back。

 namely a spell checker that they had to implement in C。

 So I came in advance with a folder called Sper and inside of this folder。

 I had code that day and all students had that week called dictionary do C。 And in this file。

 which will not look familiar to many of you if you've not taken week 0 through7 up until now。

 we did have some placeholders for students。 So long story short。

 students had to answer a few questions。That is write code to do this to do this to do。 this to do。

 and one more。 There were four functions or blanks that students needed to fill in with code。

 And I dare say it took most students5 hours，10 hours，15 hours， something in that very broad range。

 let me show you now how using AI， you soon the aspiring programmers can start to write code all the more quickly。

 not by just choosing a different language， but by using these AI best based technologies beyond the duck itself。

 So what I've done here on the righthand side of Vs code is enabled a feature that C 50 disables for all students from the start of the course called Copilot。

 This is very similar and spirit to products from Google and anthropic and other companies as well。

 But this is the one that comes from Microsoft and in turn Github here。

 And it too gives us me sort of a chat window here。 And this is just one of its features。

 For instance， if I wanted to implement to get started the check function。

 I could just ask it to do that。 Iplement the check function。 And how about。😊。

Using a hash table in C， I'm going to go ahead and click enter。Now it's gonna work。

 It's using as reference that is context， the very file that I've opened。

 which is dictionary dot C here。 Copilot in general。

 as well as a lot of AI tools are familiar with CS50 itself。

 because it's been freely available as opencourseware for years。

 What you see here at doing essentially thinking that's a bit of an overstatement。

 It's not really thinking it's trying to find patterns in what the problem is I want to solve among all of its training data that it's seen before and come up with a pretty good answer。

 So for today's purpose， I'm going wave my hand at the check G like explanation of what to do that appeared it right。

 But what's juicies to look at here is on the left。

 if I now scroll down is highlighted in green is all of the suggested code for implementing this here check function。

 Now it might not be the way you implemented it yourself。

 But I do dare say this has hints of exactly what you probably did when it came to implementing a a hash table。

 And in fact， I can go ahead and keep all of this code。 if I like how it。😊。

Let's assume that's all correct there。 It might be the case that I want to now implement the load function。

 So how about now implement load function enter as simple as that。

 And what data is being used few different things。 It says one reference。

 So it's indeed using this one file。 But there's also what are called comments in the code with which all students are now familiar theselash commands in gray that are giving English hints as to what this function is supposed to do。

 there's implicit information as to what the inputs to these functions。

 otherwise known as arguments are meant to be， what the outputs are meant to be。

 So the underlying AI called copilot here kind of has a decent number of hits hints and much like a good T or good software engineer。

 that's enough context to figure out how to fill in those blanks。 And so here too。

 if I scroll down now， we'll see in green some suggested code via which it could solve that same problem as well。

 the load function。 And I dare say I've been talking for far fewer minutes than C 50 students spent actually。

😊，The solution from scratch to this here problem。 So I'll go ahead and click Keep。

 I'll assume that it's correct。 But that's actually quite a big assumption。

 And those of you wondering like why have we been learning this。

 if I could just ask in English to do my homework for me。

 I mean there's a lot to be said for the muscle memory that hopefully you feel you've been developing over the past several weeks。

 The reality is， if you don't have an eye for what you're looking at。

 There's no way you're going be able to troubleshoot an issue in here， explain it to someone else。

 make marginal changes or the like。 and yet what's incredibly exciting even to someone like me。

 all of the staff， friends of mine in the industry is that this kind of functionality and AI amplifies your capabilities as a programmer。

 sort of overnight， once you have that vocabulary that muscle memory for doing it yourself。

 the AI can just take it from there and get rid of all of the tDium。

 allow you to focus at the whiteboard with the other humans on sort of the overarching problems that you want to solve and leave it to this AI to actually solve problems for you。

 a fun exercise too might be to go back at terms end and try solving any number of the courses a。😊。

For instance， let me go ahead and do this in my terminal window here。

 I'm going go back to my main directory。 I'm going create an empty file called Mariio do C that has nothing in it。

 and I'm going to go ahead in my chat window here and say please implement a program in C that prints a left aligned pyramid of bricks using hash symbols for bricks and use the C 50 library to ask the user for a non negative height as an integer period。

 I dare say that's essentially the English description of what was for CS50 this year problem set one to implement a program called Mariio C。

 This too is sort of doing its thing。 It's using one reference。 It's working。

 It knows as a hint that this file is called Mariio C and it's seen a lot of those in its training data over time。

 There's an English explanation of what I should do in those CS50 students in the room。

 probably recognize the sort of basic structure here of using a do while loop to prompt the user for a。

ussing the CS50 library， which has been included， print a leftline pyramid using some kind of loop and boom。

 we are done。 and these are fairly bitesized problems as you'll see as you get to terms end with your final project。

 which is a fairly openended opportunity to apply your newfound knowledge in savvy with programming itself to a problem of interest。

 it will allow you to implement far grander projects。

 far greater projects than has been possible to date。

 certainly in just a few weeks we have to do it because of this amplification of your own abilities。

 So with that promise， let's talk about how in the heck， any of this is actually working。

 I clearly just generated a whole lot of stuff and that's how we began the story with the generation of those images and those two essays by kids。

 but what is generative artificial intelligence or really what is AI itself and these are some of the underlying building blocks that aren't going anywhere anytime soon and indeed have led us as a progression to the capabilities you just saw。

 So spam， we sort of take for granted now that in our Gmail inboxes or outlook inboxes most of the spam。

s up in a folder。 Well， there's not some human at Microsoft or Google sort of manually labeling the messages as they come in deciding spam or not spam。

 They're figuring out using code。 And nowadays using AI。 that looks like spam。 and therefore。

 I'm going put it in the spam folder， which is probably correct，99% of the time。 but indeed。

 there's potentially a failure rates。 other applications might include handwriting recognition。

 Certainly， Microsoft and Google doesn't know the handwriting style of all of us here in this room。

 but it's been trained on enough other humans handwriting styles that odds are your handwriting in mind looks similar to someone else's。

 And so with very high probability They could recognize something like hello world here as indeed that same digital text。

 All of us are into streaming services nowadays， Netflix and the like。

 they're getting pretty darn good at knowing if I watched X， I might also like Y， Y， Well。

 because of other things I I've watched before and maybe up votedted in down votedted。

 maybe because of other things， people have watched to like similar movies or TV shows to me。

So that too is AI。 There's no if if if else construct for every movie or TV show in their database。

 it's sort of figuring out much more organically， dynamically what you and I might like。

 and then all these voice assistant today， Siri， Alexa。

 Google assistant and the like those two don't recognize your voice or necessarily know what questions you're going to ask it。

 there's no massive if else if that has all possible questions in the world just waiting for you or me to ask it。

 that too of course， is dynamically generated。😡，But that's getting a bit ahead of ourselves。

 Let's like rewind in time。 And some of the parents in the audience might remember this year game among the first arcade games in the world。

 namely Pong。 And so this was a black and white game。 whereby there's two players。

 a paddle on the left， a paddle on the right。 And then using some kind of joystick or track ball。

 They can move their paddles up and down。 And the goal is to bounce the ball back and forth。

 and ideally catch it every time。 Otherwise， you lose a point。 This is just an animated g。

 So there's nothing really dramatic to watch。 It's gonna stay at 15 against 12 just looping again。

 And again， nothing interesting is gonna happen。 But this is a nice example of a game that lends itself to solving it with code。

 And indeed， it's been in our vernacular for years to play against not just the computer But the CPU。

 the central processing unit or really the AI。 And yet AI does not need to be nearly as sophisticated as the tools we now see。

 for instance， here is a successor to pong known as breakout。 similar in spirit。

 But there's just one paddle and one ball And the goal is to bounce the ball off of these colorful bricks and you get more and more points。

 depending on how。😊，You can get the ball。 All of us as humans。

 even if you've never played this old school game， probably have an instinct as to where we should move the paddle。

 If the ball just left it going this way， Which direction should I move the paddle。I mean。

 probably to the left。 And indeed， that'll catch it on the way down。

 So you and I just made a decision that's fairly instinctive， but it's been ingrained in us。

 but we could sort of take all the fun out of the game and start to quantify it or describe it a little more algorithmically step by step。

 In fact， true decision trees or concept from economics， strategicic thinking， Comp science as well。

 that's one way of solving this problem， in such a way that you will always play this game well。

 if you just follow this algorithm。 So， for instance。

 how might we implement code or decision making process for something like breakout。 Well。

 you ask yourself first is the ball to the left of the paddle。 If so， you know where we're going。

 then go ahead and move the paddle left。 But what if the answer were no， in fact， Well。

 you don't just blindly move the paddle to the right， Probably， what should you then ask。😊。

Are you right below the ball。 The ball is coming right at you。

 You don't want to just naively go to the right and then risk missing it。

 So there's another question to ask， is the ball to the right of the paddle。 And that's a yes。

 no question。 If yes， well， then okay， move it to the right。 But if not。

 you should probably stay exactly where you are and don't move the paddle。 Allright。

 So that's fairly deterministic if you will。 and we can map it to code using pseudocode class like C 50 we can say in a loop while the game is ongoing if the balls to the left of the paddle。

 then move the paddle left else if the balls to the right of the pa。

 sorry for the typo there move the paddle right else just don't move the paddle。

 And so these decision trees， as we drew it， have a perfect mapping to code or really pseudocode in this particular case。

 which is to say that's how people who implemented the breakout game or the palm game who implemented a computer player Sure coded it up。

 It was a straight is that。 But how about something like Tit toe。

 which some of you might have played it on the way in for just a moment on the scraps of paper that you might have had here we have。

😊，T toe board with two o's and two x's for those unfamiliar。 This game， Tt toe。

 otherwise known as Knightights and crosses is a matter of going back and forth。

 Xs and o's between two people。 And the goal is to get three o's in a row or three x's in a row either vertically horizontally or diagonally。

 So this is a game here in mid progress。 Well， let's consider how you could solve the game of Tt toe like a computer like an AI might。

 Well， you could ask yourself， can I get three in a row on this turn， Well， if yes。

 play in the square to get three in a row。 It's as straightforward as that。 If you can't， though。

 what should you ask， Well， can my opponent get three in a row on their next turn， Because if so。

 you should probably at least block their move next， So at least you don't lose now， But this game。

 Tt toe is relatively simple as it is， it's a little harder to play when it's not obvious where you should go Now。

 all of us as humans， if you grew up playing this game。

 probably had heuristics you use like you really like the middle or you like the top corner or something like that。

 So we probably can make our next move quickly， but is it optimal。😊。

I dare say if back in childhood or more recently， you've ever lost a game of Tt toe。

 like you're just bad at Tit toe because logically。

 there's no reason you should ever lose a game oftict toe。 if you're playing optimally at worst。

 you should force a tie。 but at best， you should win the game。

 So think of that the next time you play Tit to and lose you're doing something wrong。

 But in your defense， it's because the question mark is sort of not obvious。

 Like how do I answer it when the answer is not right in front of me to move for the win or move for the block。

 Well， one algorithm you could have been using all of these years is called minimax。

 And as the name suggests， it's all about minimizing something and or maximizing something else。

 So here too， let's take a bit of fun out of the game and turn it into some math。

 but relatively simple math。 So here we have three representativetict toe boards。 O has won here。

 X has one here and the middle is a tie doesn't matter how we score these boards。

 but we need a consistent system。 So I'm going propose that any time O wins。

 the score of the game is negative one。 Anytime X wins。 the score of the game is a positive。1。

And any time nobody wins， the score is 0。 So at this point， each of these boards have these values。

 negative 1，0 and1。 So the goal， therefore， in this game of Tit toe now is for X to maximize its score because one is the biggest value available and O's goal in life is to minimize its score。

 So that's how we take the fun out of the game。 We turn it into math where one player just wants to maximize one player just wants to minimize their score。

 Allright， so quick sanity check here， Here's a board。 It's not color coded。

 What is the value of this board。😊，1， because x has， in fact， one straight there down the middle。

 So x is1，0 O is negative 1， otherwise a tie。 So now let's see how we go about with those principles in place。

 figuring out where we should play in t ta toe。 Now， here's a fairly easy configuration。

 There's only two moves left is not hard to figure out how to win or tie this game。

 But let's use it for for simplicity， It's o's turned， for instance， So where can O go， Well。

 that invites the question， well， what is the value of the board or how do we how do we minimize the value of the board for O to win。

 Well， O can go in one of two places， top left or bottom middle， which way should O go， Well。

 if O goes in top left， we should consider what's the value of this board， Is it minimal， Well。

 let's see if O goes here， X is obviously going go here， X is therefore gonna win。

 So the value of this board is going be a one， now since there's only one way logically to get from this configuration to this one。

 we might as well call the value of this board by transitivity。1。

 And so O probably doesn't want to go there because that's a pretty maximal score and O wants to minimize over here。

 though， if O goes bottom middle， well， then x is gonna go top left and now no one has one。

 So the value of this board is thus0， we might as well treat this as0 because that's the only way to get there logically。

 So now O more mathematically and logically can decide。

 do I want an end point of one or an endpoint of 0。 Well。

0 is probably the better option because that's less than one。 And thus it's the minimal possibility。

 So O is going to go ahead in the bottom middle and at least force a tie。

 And so that's where you see evidence where if you humans are ever losing the game oftictk toe。

 you have not followed that their logic。But you could probably do it if there's just two moves left。

 But the catches， let's go ahead and sort of rewind to three moves left here， there are three blanks。

 And I've kind of zoomed out The catches that the decision tree gets a lot bigger。

 The more and more moves that are left， It gets sort of bigger and bushier and that it's essentially doubling in size and with。

 And that's great。 if you have the luxury of writing it down on a piece of paper。

 But if you're doing thiss on your head while playing against a fifth grader， if I may。

 you're probably not drawing out all of the various boards and configurations。

 trying to play it optimally， you're going with some instinct and your instincts might not be aligned with an algorithm that is tried and true。

 minimax that will ideally get you to win the game。

 but at least will get you to force a tie if you can't win。😊，But Tit is not that hard。 I mean。

 how many different ways are there to play T ta toe。

 We could write a computer program to pretty much play Tit toe optimally。

 We could use code like this if the player is X for each possible move。

 calculate the score for the board at that point in time and then choose the move with the highest score。

 So you just try all possibilities mathematically and then you make the decision。

 Most of us in our heads are not doing that， but we could else is the player。

 essentially do the same thing， but choose the minimal possible score。

 So that's the code for implementing Tt toe， how many ways are there to play Tit toe， though， Well。

 255168， which means if we were to draw that tree， it would be pretty darn big and it would take you quite a bit of time to sort of think through all those possibilities。

 So in your defense， maybe not that bad at Tt toe， which is just harder than you thought as a game。

 But what about games with which we might as adults be more familiar， Well。

 what about the game of chess， which is often used as a measure of like how smart a computer is。

 whether it's Watson back in the day playing against it or something else。 Well。

 if we consider even just the first four moves of Tit。Whereby， I mean， black goes and white goes。

 and then they each go three more times。 So four pairwise moves。

 How many different ways are there to play chess。 Well。

 it turns out 85 billion just to get the games started。

 And that's a lot of decisions to consider and then make。 How about the game of go if familiar。

 Consider the first form move 266quintillion possibilities。

 And this is where we sort of as humans and even with our modern PCcs and maxs and phones kind of have to throw up our hands because I don't have this many bys of memory in my computer。

 I don't have this many hours in my life left to actually crunch all of those numbers and figure out the solution。

 And so where AI comes in is where it's no longer as simple as just writing if elses and loops and no longer as simple as just trying all possibilities。

 you instead need to write code that doesn't solve the problem directly。 But in some sense。

 indirectly。 You write code so that the computer figures out how to win。

 perhaps by showing it configurations of the board that are a good place。

To be in that is promising and maybe showing it boards that it doesn't want to find itself in the configuration of because that's gonna lead it to lose。

 In other words， you train it， but not necessarily as exhaustive。

 And this is what we mean nowadays by machine learning。

 writing code via which machines learn how to solve problems generally by being trained on massive amounts of data and then in new problems looking for patterns via which they can apply those past training data to the problem at hand。

 and reinforcement learning is one way to think about this。 In fact， in fact， we。

 as humans use reinforcement learning， which is a type of machine learning， sort of all of the time。

 In fact， a fun demonstration to watch here involves these here pancakes。 So， in fact。

 let me go ahead and pull up a short recording here of an actual researcher in a lab who's trying to teach a robot how to make how to flip pancakes。

 So we'll see here in this video that there's a robot has a arm that can go up down left right， This。

 of course， is the human the researcher。 And he's just gonna to show the robot one or more times like how to flip a。

😊，pancake？It crosses his fingers and okay， seems to have done it well， does it again。

 not quite the same。But pretty good。And now he's going to let the robot just try to figure out how to flip that pancake after having just trained it a few different times。

 the first few times odds are the robot's not going to do super well because it really doesn't understand what the human just did or what the whole purpose of but and here's the key detail with reinforcement learning behind the scenes the human is probably rewarding the robot when it does a good job。

 like better and better it flips the more it gets rewarded as by like hitting a key and giving it a point。

 for instance， or' giving the digital equivalent of a cookie or conversely every time the robot screws up and drops the pancake on the floor。

 sort of a proverbial slap on the wrist， a punishment so that it does less of that behavior the next time。

 and any you who are parents which by definition today many of you are odds are whether it's not this or maybe just verbal approval or reprimands have you probably trained children at some point to do more of one thing and less of another and what you're seeing in the backdrop there is now just a quantization of the movements。

 X Y and Z coordinates so that it can do more of the X is in the Ys and。

The Z that LED it to some kind of reward。 And now， after you're up to some 50 trials。

 the robot seems to be getting better and better， such that like a good human。

 we'll see if I can do this without embarrassing myself can flip the thing。That's pretty good。

 I've been doing this a long time， okay。So we've seen then how you might reinforce learning through that kind of domain。

 Let's take an example that's similar to those of you who are gamers。

 anytime you've played a game where there's some kind of map or a world that you need to explore up down left right。

 Maybe you're trying to get to the exit。 So here simplistically。

 is the player at the yellow dot here， for instance。

 in green is the exit of the map and you want to get to that point。

 And maybe somewhere else in this world， there's a lot of like lava pits And you don't want to fall into the lava pit because you lose a life or you lose a point or there's some penalty or punishment associated with that。

 Well， we with this bird's eye view can obviously see how to get to the green dot。

 But if you're playing a game like Zelda or something like that。

 All you can do is move up down left right and sort hope for the best。 So let's do just that。

 Suppose the yellow dot， just randomly chooses a direction and goes to the right。 Well。

 now we can sort of take away a life， take away a point or effectively punish it。

 so that it knows don't do that。 And so long as the player has a bit of memory。

 either the human player or the code that's implementing this。 Just with a dark。😊。

that means don't do that again because didn't lead to a good outcome。

 So maybe the next time the yellow do goes this way。 And this way。

 And then didn't realize that that's actually the same la ofva pit。 but that's fine。

 Use a little bit more memory。 And remind me， don't do that because I just lost a second life in this story。

 And maybe it goes this way next time， now I need to remember， don't do that。 But effectively。

 I'm either being punished for doing the wrong thing。

 or as we'll soon see being rewarded for doing more of the successful thing。

 And just by chance maybe I finally make my way to the exit in this way。

 And so I can be rewarded for that。 Now I got 100 points or whatever it is， the high score。 So now。

 as per these green lines， I can just follow that path again and again。

 And I can always win this game kind of like me nowadays。

 like 30 years later playing Super Mario Brothers because I can get through all the work levels because I know where everything is because for some reason that's still stored in my brain。

😊，Is this the best way to play， Am I as good at Super Mariro Brothers as I might think。

What's bad about this solution， yeah。Exactly， yeah， I've moved many more times than I need to。

 And just for fun today， what grade are you in。7th grade。 wonderfulful。

 So now  seventhth grade observation is like exactly that that we could have taken a shorter path。

 which is essentially that way， albeit making some straight moves。

 And so we're never gonna find that shorter path。 We're never gonna get the highest score possible if I just keep naively following my well trodden path。

 And so how do we break out of that mold。 And you can see this even in the real world。

 Another sort of personal example is I'm the type of person for some reason。

 if I go to a restaurant for the first time， I choose a dish off the menu and I really like it。

 I will never again order anything else off that menu other than that dish because I know it is good。

 but there could be something even better on the menu。

 but I'm never going to explore that because I' sort of fixed in my ways as some of you from the smiles might be too。

 But what if we took advantage of exploring just a little bit。

 And there's this principle of exploring versus exploiting when it comes to using artificial intelligence to solve problems up until now。

 I've just been exploiting knowledge I already have。

 Don't go through the red walls do go through the green walls。 And I will get to a。😊，Soution。

 But what if I just sprinkle in a little bit of randomness along the way and maybe 10% of the time as represented by this epsilon variable。

 I， as the computer in the story， generate a random number between 0 and one。

 And if it's less than that percent， which is gonna happen 10% of the time。

 I'm gonna make a random move instead of one that I know will get me closer to the exit otherwise。

 I'll indeed make the move with the highest value Now。

 this isn't gonna to necessarily win me the game that first time。

 But if I play it enough and enough and enough and insert some of this randomness。

 I might very well find a better solution and therefore be a better player， a better winner overall。

 if I just 10% of the time ordered something else off the menu。

 I might find that there's an amazing dish out there that otherwise， I wouldn't have discovered。

 And so indeed， using that approach， can we finally find a more optimal path through the maze as was shorter there。

 presumably therefore maximizing our score in doing even better than we might have by just exploiting the same knowledge。

 So you can see this， even in the game of breakout， especially if you write a solution。😊。

In code to play this game for you。 Let me go ahead and pull up another video recording of an AI playing breakout。

 And what this AI is doing is essentially figuring out maybe more intelligently than you or I could。

 how to play this game optimally。 And what we'll see here is that。😊。

Just like the pancake flipping robot。 there's some notion of scoring and rewards and penalties here。

 So like right now， the paddles just doing random stuff。

 It doesn't really know how to play the game yet。 But it realizes after 200 episodes that oh。

 my score goes up if I hit the ball and it goes down equivalently if I miss it and it's still a little twitchy。

 It doesn't quite understand what it's supposed to do and why。 But if you do it again and again。

 and again， and it's rewarded and or punished enough。

 you'll see that it starts to get pretty good and closer to what a good human might do。

 But here's where the algorithm gets a little creepy。 if you let it play long enough。

 or if you and I the humans play long enough， you might find a certain trick to the game。

 I dare say the AI becomes a bit scarily sentient in that。

 turns out if you're smart enough to break through that top row。

 you can let the game just play itself for you and maximize your score without even touching the ball。

 something that I do find a little creepy that it just figured out how to do that without being told。

 but it's just a logical。😊，annu of rewarding it for good behavior and punishing it for bad behavior。

 So that next time you have an occasion to play breakout。

 Consider that kind of strategy as opposed to doing more of the work yourself。

 let the computer do it for you instead。 Well， what else is there to consider in this world of AI in the context of machine learning。

 Well， there's specifically a category of learning that's supervised。

 And we've been using this for years。 And in fact， our first example of spam early on。

 was certainly supervised。 Why because it was you and I who was like putting the email into the spam folder into this day。

 maybe once a day， I hit the keyboard shortcut in Gmail to say this is spam。

 you should have caught this And that is training Google's algorithm further。

 assuming it's not just a little old me， but maybe thousands of people tagging that same kind of email as spam that supervised learning。

 And that there's a human in the loop， doing at least something So spam detection might be one of those。

 But the catch is that labeling data in that way manually just doesn't scale very well。

 that would be akin to having someone at Google or Microsoft labeling every email or someone。😊。

Likes doing the same for all of the videos out there。 It's expensive in terms of human power。

 And there's certainly problems out there with so much data。

 It's just not realistic for humans to label millions of pieces of data， billions of pieces of data。

 we've got to move to an unsupervised model。 And so this is where the world starts to consider deep learning。

 solving problems using code whereby you don't even have humans in the loop in quite the same way。

 and neural networks inspired by the world of biology or sort of the inspiration for what is the state of the art。

 even underlying today's rubber duck and more generally these things called large language models like chat G and the like。

 So here pictured somewhat abstractly is a neuron and it's something in the human body that transmits a signal。

 say from left to right electrically。 And if you have multiple neurons。

 you can intercommunicate among them。 So that if I think a thought then I know how to raise my hand because some kind of message electrically has gone from my head to this extremity here。

 So that's in essence， what I remember from9th grade biology。 But it computer scientist。

 we sort of abstract all of this away。 So instead of calling these to。😊，Drawing them as neurons。

 let's just start drawing neurons as these little circles。

 And if they have connective tissue between them of sorts， we'll just draw a straight line。

 an edge between them。 So this is what a computer scientist would call a graph。

 If you have two such neurons over here leading to one neuron here。

 you can think of this as being like maybe two inputs to a problem And now one output there too。

 we can represent the notion of problem solving， which is what C 50 and intertrocourses more generally are all about。

 So let's solve a problem with a neural network without necessarily training it in advance。

 just letting it figure out how to answer this question。

 Here's a very simple two dimensionmenional world X Y grid。 and here are two dots。

 And the dots in this world are either blue or they are red。

 but I have no idea yet what makes a dot blue or red。 However， if you train me on those two dots。

 I bet I could come up with predictions， especially if you let me label this world in terms of x coordinates on the horizontal Y coordinates on the vertical。

 And then you know what we can think of this neural network very simply is representing the x coordinate here。

 the Y coordinate here and。An I want to get is quote unquote red or blue or0 or one or true or false。

 However， you want to think of the representation。 So how do I get from a specific Xy coordinate to a prediction of color。

 if I only know the coordinates。 Well from the get go。

 maybe the best I can do is just divide the world into blue dots on the left and red dots on the right。

 a best fit line if you will， based on very minimal data。 Of course， if you give me a third dot。

 it's gonna be pretty easy to reize that I was a little too hasty。 that line is not vertical。

 So maybe we pivot the line this way。 And now I'm back in business。

 Now I can predict with higher probability based on X Y， what color the next dot will be。

 You give me enough of these dots， I can come up with a pretty good best fit line。 It's not perfect。

 but here's a hint at why AI is not perfect。 but 99% of the time。

 maybe I'll be able to predict correctly and I can do even better if you let me squiggle the line a little bit and maybe make it more than just a simple slope。

 So what is it we're really doing with implementing this neural network。

 simplistically with just three neurons。 Well essentially。We're trying to come up with three values。

3 parameters， and A， A B and a C。 and what do those represent Well really just a solution to this formula that their line we drew can be represented。

 if you think back to like high school math with a formula along these lines where by it's a times x plus B times y plus some consancy and we can just arbitrarily conclude that if that value mathematically gives me a number greater than zero。

 predict it's gonna be blue otherwise predict it's gonna to be red。

 we can sort of map our mathematics， just like with tick taactau to the actual problem。

 we care about by defining the world in this way。 And so if you give me enough data points in enough data points。

 I can come up with answers for that a， that B， that C。

 thiss so called parameters in neural networks。 Now， in reality。

 neural networks are not composed of like three neurons and a couple of edges。

 they look a little something more like this。 And in practice。

 they've got billions of these things here on the screen and in which case。

 pretty much every one of these edges represent some mathematical value that was contrived based on lots and lots of training data。

 And whereas I。The computer scientists might know what these neurons over here represent because those are my inputs 3 in this case。

 And I， the computer scientists know what this one represents at the end。

 If you sort of took the hood off of this thing and looked inside the neural network。

 even though there would be millions， billion of numbers going on there。

 I can't tell you what this neuron represents or why this edge has this weight。

 It's because of the massive amount of training data that that's just how the math works out。

 And if you feed me more data， I might change some of those parameters more。

 So the graph ultimately might look quite different。

 but my inputs and my outputs are going be what I use to solve that their problem。

 So if you want to predict like rainfall from humidity or pressure。

 you can have two inputs giving that one output， advertising dollars spent in a given month。

 that might predict sales by just having trained again on such volumes of data。

 And when we get now full circle to something like C50s rubber duck and large language models like Claude and Gemini and ChaT what's really happening。

 And this is all hot off the press in recent years。

 Scshotted here are some of the recent research papers that have driven a lot of this advancement in recent years。

 you。From open AI， say a generative pretrained transformer， which is a lot to say。

 but there's the G in chat G。 And essentially this is a neural network that's been trained on large volumes of textual information that gives us the interactive chat feature that we have in the class。

 and we all have more generally in chatt itself。 So an example of what is actually happening underneath the hood of these G。

 Well， here's a paragraph that up until recent years was kind of a hard paragraph to end with the dot dot dot Massachusetts is a state in the New England region of the northeastern United States borders on the Atlantic Ocean to the east。

 the state's capital is dot dot dot Now almost anyone living in Massachusetts probably knows that answer。

 But if this AI has just been trained on lots and lots of data。

 there's probably a lot of people who say Massachusetts in part of a sentence and then the answer which I won't say yet is the other part of the sentence。

 But in this example， given that the question we're asking is sort of so far from some of the useful keywords。

until recently， this was a hard problem to solve because there was so much distance。 Moreover。

 there's these nouns that are being used to substitute for the proper noun。

 like we suddenly start calling it a state。 We call it a state down here。

 and it wasn't necessarily obvious to AIs that we're talking about the same thing as if it were just city comma state where you'd have much more proximity。

 So in a nutshell， what we now do especially to solve problems like these is we first break down a sentence or the training data or input or like into like an array or a list of the words themselves we come up with a representation of each of these words。

 for instance， the word Massachusetts， if you encode it in a certain way。

 is going to be represented with an array or vector of numbers， floating point values。

 so many so that the word Massachusetts in one model would use these 1536 floating point numbers to represent Massachusetts。

 essentially in an n dimensionmensal space。 So not just an X Y plane。

 but somewhere sort of virtually out there。 And then and this has been the key to these GPS an attention is calculated based on all。



![](img/24ee856e37b0fd5c7eff7d735daa31d1_9.png)

That data， whereby in this picture， the thicker lines imply more of a relationship between those two words。

 So Massachusetts and state is inferred as having a thicker line。

 a higher attention from one word to the other。 whereas our A's and our is is and ours have thinner lines because there're just not as much signal to the AI as to what the answer to this question is Meanwhile。

 when you then feed that sentence like the state's capital is one word per neuron here。

 the goal is to get the answer to that question。 And even here。

 this is way smaller of a representation than the actual neural network would be。 But in effect。

 all these LLMs large language models are are just statistical models。

 like what is the highest probability word that it should spit out at the end of this paragraph based on all of the Reddit posts and Google search results and encyclopedias and Wikipedias that it's found and trained on online。

 Well， the answer hopefully will be Boston。 But of course，1% of the time， maybe less than that。

 the answer might not be correct。 And even C50's own duck is fallible even though we've written lots of code。

To try to put downward pressure on those mistakes and those mistakes are what we'll call。Lastly。

 hallucinations， where the AI just makes something up。

 perhaps because some crazy human on the Internet made something up。

 and it was interpreted as authoritative or just by bad luck because of a bit of that exploration。

10% of the time，1% of the time， The AI sort of veered this way in the large language model and the neural network and spit out an answer that just。

 in fact， is not correct。 And so I thought I'd end for today on this final note。

 a poem with which many of us might have grown up from Shell Silverstein here。

 about the homework machine， which years ago， somehow sort of predicted the state we would be in with these AI machines。

 He said the homework machine， Oh the homework machine。

 most perfect contraption that's ever been seen， just put in your homework， then drop in a dime。

 snap on the switch。 And in 10 seconds time， your homework comes out Quick and clean as can be。

 Here it is 9 plus4。 And the answer is 3，3， Oh me， I guess it's not as perfect。

 as I thought it would be。😊。

![](img/24ee856e37b0fd5c7eff7d735daa31d1_11.png)

This then was CS50。😡，See you next time。