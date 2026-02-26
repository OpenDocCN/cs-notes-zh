# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p13 20231003-Oct 3_ Backtracking.zh_en -BV1Mh7RzaEL2_p13-

![](img/2ac539d2b7438fd9d7fdf3ef73051594_0.png)

![](img/2ac539d2b7438fd9d7fdf3ef73051594_1.png)

All right。

![](img/2ac539d2b7438fd9d7fdf3ef73051594_3.png)

So。啊。One quick administrative announcement the homework cycle is continuing so homework six is out homework five is nominally due today i'm expecting based on how students seem to be reacting that there'll be a lot of no fault extension requests that's fine that's why they're there。

嗯。U， but one thing I do want to announce because we discovered this when we were scanning in the midterms that there were people who didn't realize that they weren't enrolled on grade scope。

So every single one of you individually。Please log into GrSpe and make sure that you are getting credit for your homework that someone else submitted on your behalf。

We can recover。If somebody submitted group homework and didn't tell gradecope who all the group members are。

 we can retroactively change that， provided your group members names are on the first page of the PDF that you uploaded。

Um， which is why we ask you to put your everybody's name on the first page of the PDFs that you upload。

Yeah， so we are hoping to have I'm hoping to be able to report。

Midterm grades a week from today in class。I think more realistically。

 the grades will come out on Wednesday and I will talk about。The in class on Thursday。

I will have office hours。prettyt much all afternoon。

 Thursday and all day next Friday for people who are concerned about how the midterm went and in particular who want or need to make a decision about dropping the class before the drop deadline。

 which is 11，59 pm a week from Friday。So we have an absolute hard deadline。I must be able。

 the TAs all know this， the CAAs all know this， an absolute hard deadline that I must be able to bring the grades to you Thursday morning in class。

I'm hoping that we'll be able to get it done earlier， but I can't promise that。Okay。Sow。Today。I。

Want to talk。About a different type of recursive algorithm than we've seen over the past week。

Most of what we've seen over the past week falls under the heading of divideide and conquer。

So you take your problem instance and you then you， by doing a little bit of work。

 reduce it to a small number of instances that are each a constant factor smaller， so merge sort。

 you sort the first half you sort the second half。😡，Ktsuba。

 you take your end digit numbers and you divide them into n over two digit numbers。

 you recursively multiply those N over two digit numbers and then you do some math。系。

The algorithms I'm going to talk about now。Are。嗯。What are usually referred to as。

Backtracking algorithms。嗯。In this case， I'm going to also do the same recursion stuff。

 which means I'm going to reduce a given instance of a problem to smaller instances of the same problem。

 but for backtracking algorithms，😡，The distinction is the smaller subpro are usually only smaller。

By an additive term， not by a constant factor。So I'll reduce one instance of size n to one or more instances of size n minus1 or n minus2。

U。This is necessarily going to lead to exponential time algorithms。

But I'm not going to worry about efficiency for now。系。What I'm really doing is setting up。

Some infrastructure in your brain。So that on Thursday。

 we can start talking about dynamic programming。But。This is。Really， you know。I'm trying to to。

You used to developing these dynamic programming algorithms systematically。

 which starts by setting up a recursive backtracking algorithm。

But there's a more general piece of advice。That I。Want。To。

You do apply to every algorithm problem you ever see ever again in your entire life。First。

 make it work。Then make it fast。Bei。So there have been a lot of questions about。😡。

This week's homework。What's the running time you're looking for？The answer is。

Faster algorithms are worth more points， slower algorithms are worth fewer points， do your best。

We have a target running time in mind if your algorithm hits that running time and it's correct and correctly analyzed and so on that it'll be worth full credit。

 if you have a slower algorithm， it will be worth less if you have a correct algorithm correctly analyzed no matter how slow it is。

 you will get partial credit。😡，Three out of 10 is a sort of minimum baseline。

If your algorithm is faster than the running time we have in mind。

 you will get more than full credit。The largest credit I've ever given in this class。

For a 10 point problem is 25 points。Only once。But I've given out you， several 20s in the few 15s。系。

Probably not on Home  five or Home six， but maybe something like that might show up on Home 7。

So'm this is sort of a deliberate thing， partly because we don't actually know how to prove。

That we have the best possible algorithm except in a few very， very special cases。

So this is real life。You find the best algorithm you can。

And possibly with the help of the research literature。

 this is the best algorithm anybody knows how to do。

 but that doesn't mean it's the best algorithm possible。

And there are lots of instances where problems have been stuck at a certain running time for。

30 years and then somebody finds a way to improve it。So this is the general strategy。

 part of the reason why we don't tell you the target running times is because then roughly half of the class will turn in algorithms that have the right running time but don't work。

😡，Um， which means you're going to hurt yourself， u don't do that， right first make it work。

Then make it fast so I'm going to be talking about exponential time algorithms。

 but most of them will be able to make fast not all of them most most of them will be able to make fast later all right。

 but I want to start off。😡，With one of the。Earlies known backting algorithms。

This is the eight queens problem。Which was first。As far as we know， studied by Gauss because Gauss。

 of course did everything first。No Gauss just like to pretend he did everything first。

 but here we actually have some evidence the eight queens problem is you're given a chessboard does this eight by eight grid。

And you want to put eight queens onto the chess board so that no queen is attacking any other。

 so for those of you who are not familiar with the rules of chess。

 a queen can capture any opposing piece that's in the same row or the same column or the same diagonal in either direction as far away as you like。

😡，So that queen in the middle on the left attacks all those squares that I've drawn lines through。

And you'll notice none of the other queens are on those squares。

 and that's true for every queen on the chessboard。U，So what Gaus。

 the question that Gaus was asked is， how many ways are there to do this？m。

And so he sat down one afternoon and found 92 solutions and wrote in to his friend and said。

 I found 92 solutions。啊。Using。What he called。啊。Meodius。That's an urine。Which means。

m methodically groping around in the dark。Tatanran it is a Germanization of a French word that Taanier which includes in its root。

 the French word for Topj so it's literally。Wandering around in a dark room。

But doing it methodically。Okay。So u。I'm going to describe how Gas did this。

But the eight queens problem。For purposes of our class。Is completely trivial。

The problem has constant size。And therefore， it can be solved in constant time。

That's not really interesting， so what I really want。Is the end queens problem？

So what I'm given really the input is just the integer N， but I imagine I'm given an n by n grid。

And I want to put n queens down on that grid so that no two queens are in the same row in the same column in the same forward diagonal or in the same back diagonal。

And the way。Gaus recommended solving this problem。His methodical groping strategy。

Let me draw out the grid here。Is to say， well。I got to put a queen on the first row。

I have no idea where the queen is going to go in the first row。

 maybe it'll go in that square in the upper left corner。Um， I don't know where the queens goes。

 I don't know how many ways there are to place say Queens that starts with that that first queen on that first row。

But what I'm going to do is I'm just going to try。Puttting the queen on that row and then filling in the rests of the grid using the same methodical grouping strategy。

So I don't know where the queen goes on the second row， but I can kind of figure out quickly。

 it can't go here because that's in the same column as the first queen and it can't go here because that's in same diagonal is the first queen。

 but maybe it goes here。All right， let's see what we can do from that so now i'm going to recursively fill in the last six rows of the grid using the same methodical groping strategy。

 I don't know where the queen goes on the third row it can't go here can't go here， can't go here。

 can't go here but maybe it goes here。And I'm going to try that and then I'm going to recursively fill in the last five elements。

 the last five rows， with the grid using the same methodical gring strategy。

Let's suppose the recursion ferry comes back and says there are 13 ways of doing it。

 starting with those three queens。Then。Gauus's strategy says， oh， okay。

Well that's not the only place that Queen could be， it could also be here。

 and then I'll continue I'll recurarse again。To fill in the last five rows or the queen could be here。

 I'll recurse again， or it could be here and I'll recurse again。

And after trying all those possibilities for where the queen can go on the third row。Says u， okay。

 well I don't， I don't really know that if that's the only place the queen can go on the second row。

 let me try putting this queen here。And then I'll recursively fill in the bottom six rows。And then。

I'll try here。And then here。And then here。And then here。And then I'll say。

 that was all the possible places that I could have put the queen on the second row。

 I'm done with that recursive call， so then I'll pop all the way back up to the top and say，Well。

 another place that could go in the first row is in column2。

And I'll recursively fill in the rest of the grid。Or in column three。

 we're recursively fill in the rest of the grid or in column four。

 so what the strategy looks like is。For all possible ways of placing the queen on the first row。

Gout a queen there and recursedively fill in the rest of the board。

And then the recursive call is for all possible plays of putting a queen on the second row that doesn't attack the queen on the first row。

Try putting the queen there and then recursively fill in the rest of the board eventually the recursion' is going to bottom out when I try possibilities for the last row and some choices of earlier recursive earlier placements of the queen are going to forbid any placement of the queen on the last row。

 the recursion might just get cut off that branch of the multiverse just gets pruned away。😡。

And others will give me a few possibilities。Okay。So。嗯。One thing to think about carefully though。

 is when I say recur。What。Problem am I actually solving recursively？

I'm not just putting as many queens as I can into the bottom half of the grid。the description。

The recursive problem that I'm solving。As to take into account the queens that I've placed on the board already。

So。嗯。The right way to say this is how many。Ways。Are there？To place。And Queens。On an N by N board。

If the first。A queens sorry。呃。If。Queens。Our。Already。On the first。And Rose。At positions。

Let's say Q from1 through R。Okay， so initially， my top level call。

 I haven't placed any queens at all。And so R is equal to zero。

 and I'm not passing any extra information in。When I placed the queen on the first row and make a recursive call。

 that recursive call sets one of the parameters is r is equal to one。

 and I've got the column in which the queen on row1。Is sitting。

When I'm recursing in the state that you see on the screen now。

My recursive call has r is equal to four， and in this case Q is equal to 25，3，8。

 right r is equal to four。Okayy。😊，嗯。So this is something I'm going to harp on a lot when we're describing a recursive algorithm。

 the first thing to do is to figure out what problem that it's solving。

You're seeing a little bit of this in the homework that you're working on already this week。U。

But I want to make it clear。That I'm describing a problem that can in principle be solved recursively。

Right。Another example of this is suppose I want to find the median element in an uninssortted array。

Well， I can use Quick select。But when Quick selectlect makes recursive calls。

 those recursive calls aren't necessarily looking for the median of those subs。

 it's looking for something in a different rank， so I have to add in some additional information so to say。

 actually I'm not just looking for the median， I'm looking for something at an arbitrary rank。Okay。

可以。So I need some additional information here。About。Past decisions。In order to make。Further progress。

U。Sorry， I believe actually。Aly in the first。R minus1 rows r minus1， so in this case。R is equal to。

5ve。Okay， so here's the pseudocode that Gauss did not write。

Gauus's algorithm was later rediscovered by a French mathematician named Laquire。

 who read about the Queens problem in one of。U u。Lucas's newspaper articles。

 the same guy who invented the Tower for O。So the idea here is if R is equal to n plus one。

 that means I'm about to try to fill in the robe below the bottom of the board。

 this means the first n rows of the board are actually filled already in that case I just print out the positions of all the queens so what this is actually doing is not asking how many but just print them all out。

😡，If R is less than n plus one， so I'm trying to put a queen on the R row and below。😡。

I try all possible columns。So this is the。Column index。Of where to put the queen on the R row。

There's this for loop in the middle that sets this variable legal。

 this is just checking whether a queen on row R column J attacks one of the queens on the first R minus1 rows。

😡，If legal is true， then this is a legal placement for the queen。

 and in that case I put the queen in Ro R at column J and then I rehearse。😡，And in this case。

 I'm actually passing the entire array queue down in every recursive call just because I guess if I were really going to do this。

 I'd probably try to set up Q as some sort of global variable so and I'm not pushing this enormous array under the S every time I need to make a call。

嗯。But there is my recursive act trackinging algorithm。Any questions about how this algorithm works？

You do the stupidest thing you can on the top row， try every possible placement。

And for each of those placements， you do something rehearsive。Yeah。这个。Oh， yeah。Here。

This is I'm filling in the fifth row。So Rs five。So the first four indices are the placements of the Queens on rows one through four。

The queen on row one is in column two， Queen on row two is in column five。

 Queen on row three is in column three， Queen on row four is in column8。

So the contents of the arrayQ is25，3，8 and another stuff I don't care about。Yeah。谢谢哈。给这个。

So the question is， at what point am I taking the queen back out？

So the semantics here is when I call place Queens Q1 through NR。

Only queens in the first are Rose matter。So there might be some numbers in later indices in Q。

 but'm not the algorithm never looks at them， even recursively。Yeah， I only care about the first R。

So that means。Intuitively， I removed the queen from the board。When I returned for my recursive call。

So。嗯嗯。Recursive algorithms generate patterns of recursion that we usually refer to as recursion trees。

 so you've seen。Recursion trees for things like algorithm analysis for doing like Mer sort you get N and over two and the two children and over four and the four grandchildren here what I'm showing you is not time。

 but the input to the algorithm for every recursive call for the four queens problem。So at the top。

 I have no queens on the board at all。In the first level。

 I'm trying all possible locations for the queen on Ro one。At the second level。

 I'm trying all possible locations for the Queen on row two， given the location of the queen on row1。

 so if the queen's in the upper left corner， there are only two legal places that I can put the queen on row two。

😡，没以。嗯。So I can put the queen here and I can put the queen here。

 but I can't put the queen in this in row2 column two because it's on the same diagonal or I can't put the queen in row2 column one because it's in the same column as the first queen I placed。

When Im down in this leftmost subproblem， no placement in the third row is legal。

This is attacked from row1， this is attacked from row2 from row 2 and from row2。So at that point。

 I don't make any more reccursive calls。That branch of the multiverse pruned away。

Loki goes back to the TVA。It is the re recursive call。Returns。And we try a different variant。Okay。

 in the end。😡，Only two of chains of recursion lead me to solutions to the two queens problem。

And so the algorithm that I showed you here that prints out those solutions would print out。2，4，1。

3 and three1，4， two。Describing those two solutions。嗯。This is half。

Of the recursion tree for n equals five with the first queen all in the left half of the row。

 so again there are five possible places I could put the queen in row one。

 I'm only showing you three of them。UmFor the upper left corner。

 there are three places I put the queen in row two。

But if I start with the queen in the middle of where I one。

 there are only two places I could put the queen in row two。U。Again， eventually。

 a lot of the options are pruned away， but eventually I find these five solutions to the five queens problem and in the other half of the recursion tree。

 I find the mirror symmetric solutions。嗯。Now。嗯。The algorithm's correctness basically follows from the fact that I'm not doing anything intelligent。

At every row， I'm trying every possibility for putting a queen in that row。And then I'm。

Recursing where I'm passing all the information about all the queens I placed。

Into the recursive call so that I can't place a queen in an illegal place。

The correctness is basically immediate。Because I'm not doing anything intelligent at all。Now。

 this particular algorithm happens to run in some ungodly exponential time。I think。

They're roughly they're in rows and。In about half of them。

 I can put the queen in about half of the cells。At least so this is going to be something like end to the order end running time。

 it's really awful。And as it turns out。We don't know anything better。

So this is at least morally the fastest algorithm we know for solving the Queens problem。没。Okay。

 so this is a subtle question， I just want to spend a little bit of time on it。So。

The one way to answer that question is， if I just want to know if there is a solution， the answer is。

😡，Yes。Unless n equals two or three。You can prove that by just constructing one solution。

 so the problem there is trivial。So what I mean here is in terms of can't do better。

Is if I have an end buy and chboard and I've already placed。Some queens on it。

But not necessarily all of them。And I want to know whether I can fill in the rest。

This is what's called the N Queens Comp problem。This is NP hard。

We'll'll discuss in later in the semester what this means formally。

 but morally what this means is this problem cannot be solved in sub exponential time。

On the other hand， the Gaus's backtracking strategy。Doesn't give you instances。

 arbitrary instances of the N queens completion problem。

 it gives you these very well structured instances where I fill in the first Rs and these last n minus Rs are blank and now I want to know whether I can complete。

And so this， I don't know， let's call it top down。In Queens。Completion。Um。This is an open question。

Nobody knows if this problem can be solved faster than next exponential time or if this problem is NP hard。

I do not recommend working on this problem。嗯。Until after you're a PhD student and you've published a couple of other papers。

This was open until。2015。Okay， so。There's a sense in which。As far as we know。

 this blind groping around really is the best you could do。

I'm only showing you this example to sort of get you warmed up to the idea of what backtracking is。

 boasted the problems we'll see there are faster solutions and we'll figure out how to derive。系。

But any other questions about？And Queens。Okay。So。Um。Let's play a different game。

So this is a game that。😡，One of my colleagues taught me to play with my kids。

At restaurants when we're bored。So the idea is。You go to a restaurant。

 there's usually a little box on the table。That has sugar packets in it and it usually has several variants of fake sugar。

 so in particular you can pull out the pink packets， those are always scharin。

 you can pull out the green packets， those are always splendor。

The blue packets are always asked per time the yellow packets are always something else。

But you set them up in this sort of 3D by 3 board and you play the following game。

 so in a single turn I'm allowed to move one of my sugar packets in its forward direction。😡。

At the beginning on the three by three board and moves alternate。Yes。with one exception。

 if it's say red's turn and red wants to move and there's a green sugar packet in front of red and there's an empty space beyond that。

 I'm allowed to hop over。😡，But then of course， in this case， my opponent can hop over。

 but then I can hop over again。Okay， and the goal is to be the first player that get all of their sugar packets to the other side of the grid。

嗯。So here's an example game。By the way， I have no idea what this game is called。

UThis is all I remember from the rules that were explained to me if you've seen this game before。

You tell me， I'd love to know what it's actually called。But you'll notice， for example， that of。

For example， here。In this position， the green sugar packet at the top can't move down because there are two red sugar packets blocking it。

And even worse in this position， red can't move at all because two of their sugar packets are already off the board in the gold region and the third one is blocked and so red has no options but just say pass。

😡，And that is actually， you know， forcing red to pass is actually what allows green to win the game。

 even though red moved first， generally， I think the first player a has a winning strategy here。诶。

All right。Simple game。Can teach the rules to a seven year old in a few minutes。Um，Uh。

 play the game for， you know， a few times I'm going to get bored， move on， but um you could say， u。

 what what if I'm going to make this to MP， I want you to write a program that plays this game perfectly。

Or whatever game you like。But I'm going to use this game as an example。Now。The way。

The game planning programs are generally done。Is by recursively exploring the space of all possible moves。

So this is something called game treee。So at the root of the game tree。

 I have my starting position for my sugar packets。m at level one。

I have all positions that can be reached by one move from the root。At level two。

 I have all positions that can be reached by level two at the root。So I have this giant tree。

And you can build game trees like this or at least define game trees like this for any game at all。

 right if you're sending across from Magnus Carlson playing chess。

There's a giant game tree that starts at the root with all the chess pieces on the board and the starting positions。

And it has， you know， in the first row， all possible places that you can make your first throw。

And in the eighth row because this magnus checkmate everywhere。Okay， and so every game。

That has no randomness and no hidden information or anything like that。

Can be described as I'm going to start with a token at the root of a tree。And on even turns。

The red player is going to choose one of the children of that node and move the token there。

And on odd turns， the green player is going to choose one of the children of where the token is and move the token there。

Whoever gets to a leaf？When it reaches a leaf on their turn winds。

So if it's your turn and you can't move。You lose。So lots of perfect information to player games can be abstracted this way。

So。What how do I how do I play this game perfectly well what I'm going to do is I'm going to say。

 well I don't know what my best first move is I just saw this game for the first time five minutes ago。

 I'm going to try all three possible first moves。And then I'm going to try to ask the recursion fairy。

 hey， were these any of these moves do any of these moves allow me to win？Now， what this means is。

If a position allows me to win， that means no out， no matter how my opponent moves， they must lose。

 assuming we all play perfectly。So we have this notion of sort of good positions and bad positions。

That we can untangle by following this recursive backtracking algorithm。

So the input to the algorithm is。Um， something I'll call the state of the game。

 the position of all the pieces on the board。And a boolean that tells me。Which players turn is next？

Whose turn it is， is it me or is it the other guy？嘿。So a game。Game。State。Is a positions？

Of all the pieces。By。So' if I reach a state where I've already won。

Then I think this is a good position。If I reach a state where I've already lost。

 then I think this is a bad position。Otherwise， the interesting thing is I'm going to take the given game state and I look at all possible legal moves。

From the given game state X to some new game state Y。And I'll ask， hey。

 is that game statewide bad for the other player？If that game stand is bad for the other player。

 then it's good for me， that's a move I want to make if I make this move that tells me I can guarantee that there's going to be a win。

Because。With perfect play。It doesn't matter the other player can't win， it's a bad position。嗯。

And so if there is a move that I can make。That gets to a position that's bad for my opponent。

Then I know that I can force a win and so the position that was given at the beginning is good。

If all of the moves I can make。Lead to positions that are good for my opponent。

Then it doesn't matter what I do， I will lose， this is the bad position for me。Right。😊。

So a position is good for me if all following positions are bad for my opponent。Or any， sorry。

 it's good for me if any following position is bad for my opponent。

It's bad for me if all my following positions are good for my。Yeah。

This tells me given the current position， if I play perfectly， can I force a win？都对。Well， okay。

 so the question is there's nothing here that telling me what moves I should make。

 except I can modify that， I can modify the algorithm。All， so in this position。

I actually don't just discover that x is a good position， I discover a good move。😡，In that position。

And this will bubble up through the levels of recursion。

So I know I should move here and then if you move to somewhere else。

 I can do this again and I find another good move。If there is a good move。Otherwise。

 I should just resign。系。So I can recover the actual sequence of good moves from。

The trace through the recursion if I want it。Um， or at least at the very top level。

 I can know whether there's a good first move and I and I can make it。嗯。

So this is another example of a canonical example of a recursive backtracking algorithm。

I'm thinking about all my possible first moves， and then I'm thinking recursively about all of my opponents。

 possible next moves， and then recursively about all my possible next moves after that。And so on。

 there's this weird kind of alternation that good for me is bad for my opponent， but。

The core of it is really doing a full exploration of this game tree。

And so the recursion tree for this play any game algorithm is exactly the game tree。

But there's one distinction between this backtracking algorithm and the algorithm that I showed you before。

What do I need when I'm evaluating a current state of the game in one of these subproble？

What do I need to remember about？My past about how I got here。For the eight queens problem。

I had to remember every decision I made previously in higher level for recursive calls。

 I had to remember exactly where the queens were。But here。

I don't actually care about the sequence of moves that got me to this position。

There are two different sequences of moves that get to the same position。

 that position is good or it's bad regardless of how I got there。

So I don't need to remember the full history of the game I only need。To remember。啊。

The where the pieces are now， basically。Right。And this is something important about some backtracking algorithms。

 sometimes you have to remember your complete past。Imagine that you you're。

Thinking of this as trying to construct a sequence of decisions in the gameplay program。

 you're trying to find a sequence of moves that leads to victory。

When you're in the middle of that sequence trying to figure out whether there's a good sequence of moves。

 you don't actually care what your earlier moves were， you just care where the pieces are。

If I reach the same state of the game through a different sequences of moves。

 I'm going to get the same answer。So I'm passing around less information。Then I did。

In the eight Queens Pro。Right。Again， the analysis of this obviously depends on the game and what it means for their legal move and the analysis of the sugar packet game runs in constant time because there are only six sugar packets。

ait，But I have no idea。About any results about the N sugar Pra game。It's probably NPP hard， actually。

 it's probably piece based hard。But。Nobody's proved that nobody knows anything about this game。Um。

 nobody cares about this game。Except me and my kids， maybe。When we were bored。

But any questions about about gameplay in general？And about this sort of backtracking strategy。Yeah。

 so in this abstract treatment that you' created。You have different branches and each of branch instead a number of winning and leaves you think of them as and then those leaves that have if you're drinking green winning。

 those give you a like number of states which you win in this decision so the way that I've described this algorithm here。

 I've just returning a boolean good or bad。You can modify the algorithm to say something like。

How many good booms do I have in this direction or how many good paths。

 how many paths to victory do I have？Then you'd be doing some more math instead of just true false logic。

There are other things you can do in practice。What would you don't actually explore the whole game tree。

 use some heuristics to say， you know what， I've got more sugar packets than the other guy this is probably a bad position for me。

 he's already got stuff across the finish line， let me just declare this to be a bad position and prune anything below that。

So real chess engines like stockfish。Include a game tree search out to about eight or nine levels。

And then do some AI stuff。To go beyond that。But then they just sort of use heuristics to judge how good positions are and optimize how they do the search to look at more likely good positions first and less likely good positions later。

So there are lots of heuristics that go into actually playing games in practice。

Playing games computationally in practice， but also I guess as a human player in practice。

 nobody explores the complete game tree either。嗯。But if I really want absolutely to know。

Perfect gameplay， this is what I have to do。Right。So these are the two classical examples of what backtracking looks like。

I want to show you a third。嗯。Which？Isn' it normally thought of as an application of backtracking。

 but is a real world problem or at least was a real world problem 2000 years ago？This is Latin。

The way it used to be written。You'll notice that there are a couple of things that classical Latin didn't have。

One of those things is lower case letters。Lower case letters were invented by Irish monks in the7 century。

To aid in readability。But there's something else that's missing。Spaces。

Spaces were invented by Irish monks in the seventh century。

When you read Latin the way it was written 2000 years ago。嗯。One of the tasks that you had to do。

 your brain had to do is figure out。That they're where the word boundaries are。呃。

So that's syn and on。Primus de Gas Intan Tenui'sient unknown protest。嗯。So there was a period of time。

When Latin wasn't written in what is called script， the continuous script。But rather。

You would put little dots。In between the words。Called。Interpumped。Or interpunks。

Inter just is the Latin prefix that means between pump is the Latin word for point。😡，Okay。

 so you put points between the words。Um， so。The problem that the classical Latin reader had。

Is where to put those points？This particular Latin sentence， by the way。

 is from a speech by Cicero who was。呃。嗯。Basically playing Johnny Cochran in a trial。

Remember Johnny the wait？Do you remember Johnny Cochran do you remember。

 do you know who OJ Simpson is， okay， there was a trial， you know。

 OJ Simpson tries to put on this glove and it doesn't fit and Johnny Cochraran says it doesn't fit。

 you must quit。m so this is the the Latin equivalent of it doesn't fit just to quit he was actuallyum on the opposite side of the case from a former friend of hisum who and he's he's saying noh you're not a legal scholar that's not that's not you know you you're not doing anything important that basically says no。

That's trivial stuff。Actually， let me see if I can find， I'm sure I can find the exact quote。

You're a。First of all， dignity in such paltry knowledge is impossible。This is trivial stuff。

 mostly concerned with individual letters and the placements of points between words。😡。

Inter pununctu onibu。Is putting points between words。

So let's abstract this into the following problem， I give you a string。

And I want to know whether it's possible to decompose it into a sequence of words now I'm going to imagine there's some oracle out there that will tell me what a word is。

😡，You've actually seen this problem before。So if a word is an element of some regular language L。

What I'm asking， is that string a string in the language L star？

Can I decompose his string into chunks， each of which is a string in this language L。

 but let's imagine for intuition that what I mean by a word is it's a word in the Scrabble dictionary？

It's a word that well a Scrabble dictionary is not a good idea。

 it's a word in some you know dictionary that only contains things that you actually recognize as words。

So blue stem unit and so。I want to know whether it's possible to split this string into English words。

 and I'm going to imagine。That I've got a function called is Word。That returns true。If W is a word。

And false。IfW is not a word。Otherwise。Okay， just I'm going to assume that。So the problem is。Given。

A string。So I'll usually， you know， put it in an array like this。Is a the。Concatenation。Of。Words。嗯。😊。

So。What do I do？I start at the beginning and I go， well， let's see， a word is some prefix。

 if it's going to start at the beginning of this string， I don't know which prefix it is。

Let me try them all。For each prefix， I cut that prefix off and I recursively asked for the rest of the string。

Is displable in words？And so in that recursive call， I would look for another prefix。嗯。

So when I'm deep inside this recursive subproblem， maybe I've decided I'm going to take blue is my first word。

 then STEM then unit then robots。😡，And I'm left with these characters here。I go， well。

 just look at the string H， is that a word no？I look at the string he， I go， a， he is a word。

Maybe that's the next word in my decomposition of this string into words， so let me。😡。

Cut off the string。Caught off that word。And now recursively。Try to decompose the rest of the strain。

If that works， great， I'm happy if that doesn't work。Then I will look for longer things。

 so sorry HEA isn't a word。But HEAR is a word。So I could cut it off here。

And try to break down the rest of the string if that works great， if not。Well， heEART is a word。

So I'll try cutting off those five letters and recursing on the rest。If that works great， if not。

I'll cut that off HEARTH is a word。So I'll try cutting off those six letters and we'recrively decomposing the rest of the string。

I think this is the last prefix of this word here in the white box that's actually an English word。嗯。

So I would make like four different recursive calls。So I have in this recursive subproblem。

 I have no idea what the first word in a legal decomposition might be。So I tried them all。

Totally brute force。Just try everything for every prefix， check if it's a word， if it is。

 cut that prefix off and recur。😡，嗯。So everybody understand what the strategy is。No。

What do I need to remember about my past？When I'm thinking about this strategy。

I jumped into the middle of breaking down the string into words after I've chosen the first four。

 and now I'm trying to figure out what the fifth word is。

What do I have to remember about those past decisions？In order to make。Consistent future decisions。

Yeah，或者个期在。Does it I mean， so let me just scroll up here。Do I really care？What those prefixes are？

The answer is nothing。I don't care about my the only thing I do need to know is how long this suffix is that I'm considering recursively。

That I need to know where I am in the input strip。😡。

This is the analog of when you're doing language transformation。

 I need to remember the state in that DFAM。But I don't need to remember anything else。

 I don't need to remember whether the first word was blue or blueist。

Or whether the third was unit or nitro， doesn't matter。I reached。

heartar hand Saturn spin or hearth and sat urn's pin。

Or whatever I reached the same suffix through two different ways， doesn't matter how I got here。

The subpro， the input to the subproblem is this suffix and nothing else。

So the actual recursive problem that I want to consider is。Given。Any suffix？A from I through n。

Is well， actually， sorry me just。Sayid this differently is。The suffix。A from I through N。啊。

The concatenation of words。I don't care how I got there。I'm just in the middle of the process。

 I've got a suffix to break down， okay？I'm just going to throw the suffix to the recursion ferry。はい。

rather， if I get the suffix， I'm going to try to pull off the first word and for every possible first word I'm going to throw the rest of that suffix to the recursion ferry as a smaller suffix。

😡，When I'm recursing the size of my suffix is always going down。

 so I know that the recursion will eventually bottom out。Um。

 but I don't need to remember anything at all。About my past decisions。Just the suffolix。系。So here's。

Some pseudocode。Sable takes in an array A and tells you whether it's splitable that string is splitable into words。

 so if the array is empty， that means the length of the array is zero yes。

 the empty string is splitable into a sequence of zero words。😡，So evacuuously， the answer is true。

 the empty string is always an element of L star。Otherwise。I try all possible prefixes。A1 through AI。

For all indice's I， and I asked， is this prefix a word and if it is。

 then I ask the recursion fair is the rest of the string splitable？😡。

If the recursion fairy comes back and says， yes， the rest of that string is splitable。

 then I've got a decomposition of the whole string， the prefix that I picked out。

 plus the decomposition that the recursion fairy。So I return true。If the recursion ferry。

 none of the calls to the recursion fairry succeed。

 then there is no first word that I can pick out of the string that will lead to a legal decomposition。

 and so I must return false。😡，可以。Again， correctness follows because I'm doing nothing intelligent。

I try every possible first word。In fact， I look at every possible prefix and ask， is this a word。

 if it is， maybe it's the start of a decomposition。

 ask the recursion fairry about the rest of the strain。嗯。If it's not a word。

 then it can't be the first word in the decomposition。Sorry completely by brute force。Now。

 you may have some idea in your head when you're looking at this that， oh。

I know there aren't any words with more than 17 letters in them。

 so I don't actually have to go from I equals1 to n because I know that his word is going to return false。

 No， you can't say that because I didn't tell you what it means to be a word I just used some examples and I believe interpunionobus has more than 17 letters。

 it's very easy to like think， oh， this is obviously not going to work， I don't need to look。

 or this is obviously going to work， I don't need to check。Don't do that。I just blindly grope around。

 try every possibility and see where it goes。Yeah。Yes。么。It was looking for the。

Word and the letter the word is longer than the longest word in the dictionary can you stop？Sure。

 but I didn't tell you what is word actually does， it's a magical oracle。

Maybe it contains arbitrarily long strings。Don't know。Doesn't matter so yeah。

 if there is a maximum word length， then yes， you can prune at that maximum word length。But。

Maybe this is German and there is no maximum word length。系。Now there's one。

Sort of a bit of inefficiency in this algorithm， which actually is going to make this quite a bit less efficient than it needs to be。

 which is I'm pushing arrays around。I'm actually passing in this entire array as an argument to the recurseth call。

 that's a little bit silly when what I could do instead is just pass in the index。

That describes that。Suffix。Into the recursive call。So' going this is the same algorithm。

 I'm just expressing it slightly differently so that instead of passing an array as the argument to my recursive function。

I'm just passing in a single integer I， a single index。So what this function does is it returns true。

If the suffix starting at the given index。It's splitable。

And the actual string that you were given as input， I'm just treating as a global variable。In fact。

 I'm really。Treating this as a global variable even inside is Word。

 I can imagine writing is word as give me two indices。

 and I will tell you whether the substr starting an index sign ending an index rate is a word。😡，系。

If you actually implemented it like this， this would be a lot more efficient because I wouldn't be passing these large blocks of memory around on the stack。

I would just have one global array that I could refer to。

Those of you who think global global variables are evil， good， we'll fix that on Thursday。

 but for now， just make it work。嗯。系。嗯。This function， this recursive function， I can also express。

Quote unquote， mathematically。As a recursive function。In quote unquote， more mathematical notation。

But this is the same function， splittable of I returns true if and only if the suffix starting an index I of my original input string is splitable。

😡，I've just written it in different notation。So the case I is greater than n。

 that means I'm looking at the empty suffix。😡，My pointer into the string has run off the right end。

So the empathy suffix is vaculously splitable into zero words。Otherwise， this is。啊。An ore。

Whenever you see a symbol that has like something equals something below it and something above it。

 it as a programmer， you should pronounce that for loop。Sigma。

 that it's pronounced for loop pi that's pronounced for loop。With an ore inside of it in this case。

So this is taking over all possible values J。I look at whether the substr from I to J is a word and the rest of the string is splitable。

😡，And then I'm oring all those options together， so if there is any index J such that I have a word at the beginning and a splitable string at the end。

Then I'll return true if all of my options are bad， then I'll return false。ok。Now。

Let me stop and ask if there are any questions about how this backtracking algorithm works。

Try all possible first words， cut them off for curse。嗯白了。啱。😡，Now。

It turns out if you analyze the running time of this algorithm。It's exponential。

there are about two to the n ways of splitting a string into substrs for every possible gap between two adjacent characters。

 you can either split there or not。😡，So you've got about two to the end different ways of splitting n characters into substrates。

In the worst case。Every string is a word and except having the last character in your input。

 so all strings of A's are words， and I gave you as input the string 10 million A's followed by an X。

In that case， you'll actually explore recursively all possible ways of splitting the input string into words。

Into substrates， actually。So it really is two to the end。嗯。

But there's something really weird about this。What values can number that variable I have？

It's an index into an array of size and。So how many different values？Can the index I have？And。😡。

I can call splittable one， splittable2， splitable3， but splittable 48，able 374。

 splittable n minus1 splittable n。Nothing else。So this recursive function。

Only has n different ways of calling it。There's only any different ways in all of this weird recursion。

 exponentially large recursion tree that I'm going to build。There are only n distinct sub problems。

But I'm running in exponential time。What's happening is。I'm visiting the same subproble。

Multiple times。And the recursive backtracking algorithm has no memory。😡。

When it sees the sub problemble it goes， okay， I'll try all possible first things。

 cut it off recurse， then it gets the same string again and says， okay。

 I'll try all possible first words， got them off and recurse。

It's repeating the same work that it did previously。Over and over and over and over and over again。

 ultimately， some for some inputs an exponential number of times。So。

How could I avoid exponential time？There's only1 different ways。waysay to call this function。

How do I make this more efficient？Memory。So the first time I call splittable of seven。

I look at the suffolk starting at indexd seven， I cut off a first board in all possible different ways and I recur。

 and eventually to get an answer， political of seven is true。I write that down。

And the next time I call splitable of seven， I go， oh， I already did that true。So if you write。Down。

Your results。This will actually improve the running time。From a。

Order n and order two to the n to order n squared and and I should say instead of time here this is calls to is word it's still the case that I'm going to call I'm going to try every possible substr every possible place every possible value of I and every possible value of J I will call is word of Ij。

 but they're only n squared of those。😡，Once I've called that， I'm never going to call it again。

 once I've called splitputable of I I'm never going to call splitputable of I again。

 I just look it up。And this turns out to reduce the running time of my algorithm from exponential。

To polynomial。This is the essence of dynamic programming。Do stupid， blind groping around in the dark。

Except write down what you've done。Except do it in an order so you don't have to do the blind gripping。

 but we'll get there on Thursday I'm happy to answer any more questions about this。

 but for now we are out of time。Thanks。嗯。

![](img/2ac539d2b7438fd9d7fdf3ef73051594_5.png)

嗯。