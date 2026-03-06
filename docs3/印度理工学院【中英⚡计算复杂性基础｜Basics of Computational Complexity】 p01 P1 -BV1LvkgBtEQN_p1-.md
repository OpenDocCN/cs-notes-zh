# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p01 P1 -BV1LvkgBtEQN_p1-

![](img/2c117ddb0bd12a7043b09ca966ce6a0b_0.png)

So welcome to the course on computational complexity theory。So in IET Can。

 this course is number C 640。Okay， this is a mid level course。

Its not very basic and its also definitely not advanced。

 This is a course just after theory of computation。嗯。If you have done that course。

 then some of the concepts here will be easier to。Started with。Otherwise， I will do a quick。

Recap of the basic models like tuuring machine， et cetera。

 time and space and other resources in the first first week。And after that。

 we will start building new things。New complexity classes。So， computation。

We all understand these days we all use， in fact， these days。As a process。

Running on a computer like device。So。Even the definition of what is a computer like device keeps changing as new devices come up。

So previously phones used to be not a computer， but these days smartphones are actually as good as a computer。

Right， so whatever is happening there， whatever is happening in that machine。That is。Really。

 computation。So it's a process， right， that is。That can essentially solve any problem that can be solved。

That can be automated。 So while complexity。Right， so I'm just definingfining the keywords。

Which are in the course title So what is computation and now what is complexity So complexity refers to the resources。

That this process requires。Right， so。What are the resources。

 So resources the most common resource time right how much time does it take to solve a problem。

Right， for example， if you just opened a browser and you are looking you are searching in Google。

So when you give a query， how much time does Google take to give you the results？So that is time。

So time is what is important for you and for Google what is also important with time is space。

How much space does the algorithm require because based on that Google will buy servers so these are the main resources。

How much time。How much space。And。You will see， or you must already be knowing that。

The ability to toss coins is very important for computers。

Right many practical algorithms actually do random selection。So in that case， how much of randomness。

So randomness could also be a resource。And in fact， in this course。

 we will invoke this a lot of times。It's a very important resource。So， so the previous course。

If you have done it。Theory of computation。So， this is motivated by the。

Theory of computation T U C is motivated by the question。Does every problem has a solution。

Now this solution， I not only mean mathematical solution， but also in terms of computing process。

Right， so problem may be a computational problem， and then you want to。Actually。

You should be able to do a computational process， run a computational process on a computing device。

 so that is quote unquote solution that we are looking for。

 There is no mention of resources time or space or anything in theory of computation。

That will be our business in this course。So， theory of complexity。Is motivated by。

Once there is a solution， once there is a process， what is the cheapest solution？Okay， so cheapest。

 it can be in terms of time or space。Or random bits and so on。 So， for example。We know how to。

Add and width numbers。Read given。V n bits。So this will be our usual。

Moode of representation that in the input， you are given bits。Great 0 or1。So。E has n bits。

 B has n bits。And then these two integers you want to add。So obviously。

 you know the additional algorithm from school。So there is a solution， but then how cheap is it？

Is it a fast solution。So how cheap is this。Those kind of analysis we are interested in in this course。

If we。Do it carefully。Which means if we implement the additional algorithm carefully。Then， it。

Takes time。Around so I am skipping the constant factors in the from the implementation。So。

 it will be something like。Enbits。For a and n bits for B。So， it's around2 n。

That if you recall addition， the weight goes is you start from the lowest。Please。

You add the two bits， then you get a carry。So you go to the next position。

There now you have three bits to add and so on， so its a it's kind of a single scan of these two numbers。

obviously every bit of ANB has to be seen because if you flip even a single bit in your ANB answer changes。

So you have to look at2 n bits。 and that is kind of the。Time complexity as well for addition。

 So this is as fast as it can be。 right This is very cheap。 So you cannot do it any faster。Than this。

This is linear time。But you cannot do it faster than linear time because then you would be missing some of the input bits。

And that addition is very sensitive to that。So this is a this is the example of a very simple problem and obviously a very practical problem。

 I mean you can do nothing if you cannot add numbers。呃。

And then there is the other extreme of very difficult problems。 in fact。

 problems that are impossible。Lake。We have。Uncomputable problems。Okay， so， so there I mean。

 the question of complexity would not even arise because。

The question has the problem has actually no algorithm。

 so then there is no resources required is infinite。Okay， in finite sources， you cannot solve it。So。

 that is。For example。U。Can you write a program that can read another program？

And decide whether it holds or not。That takes。Let's say， a C program。M as input。And decides。

Whether M。On execution。Hlls or not。RightSo whether the input computer program and you can assume it to be C program。

 whether it will halt or not， so this is the famous or infamous halting problem。

This cannot be solved。If you have done a course on TUC， then you already know the proof。

 but you can read the proof in standard text， it is quite easy。But very illuminating。Okay。

 another example is。Su。Think of the program M。As the following， so。

What I will do is there is a for loop。Over even numbers。Okay go over all the even numbers。Use a flag。

Now， go over crimes。Go over primes。Up to n， P less than equal to n。And。

Check whether n minus p is also prime。Okay， we took a prime P。嗯。

Less than n and with the remaining and minus p is prime。So if n minus p is prime。

 then you set the flag to1。And。Yeah， so that's the second for loop。The fall loop ends here。

So I don't need to put the bracket。 Let me just erase it。

Just go over all the primes and check whether for some P。And minus p is prime， if you find such a P。

 then you set the flag to1。Otherwise， the four second for loop continues。When this follow loop ends。

 you will check for the flag。The it is 0， which means that。No prime P was found。

Sas that n minus p is prime。So then， you will halt。Okay， otherwise。You go to the next number n。

So now， this is a。Very short program computer program M。Which is basically I mean， on the face of it。

 it is an infinite loop。It's looping over all the even numbers n。And。

It is trying to find is trying to express Ns a prime plus another prime。Okay。So P plus Q。

 can you express N P plus Q where P and Q are prime numbers？If it finds this decomposition， then。嗯。

It sets the flag to1 and it will go to the。Next number， even number。If it fails， then itll。Come out。

 the program will end。 So now the question is whether this program will halt So this we don't know。

 Okay， we don't know whether this program will ever halt or not or is this an infinite loop or not。

So that is the level of R。Ignorance。So what you can show is。This program holds。

You are a counter example。Of the goldba conjecture。So this is a famous open problem。So。

 what this program is trying to do it is trying to find a counter example okay。When it halt。

 then the n at which it halted。Is of the type that cannot be decomposed into two primes。So。

 and we don't know whether such a thing ex such an n exists or not。

Colberg conjecture says that such an end doesn't exist。So this program should never halt。So。

What this means， this small example。It is actually illuminating because what it is telling you is that。

In this way。We can encode。Almost any open math question。It's a C program。Okay。

 so you can express open math questions， mathematical conjectures as C programs。And。

Then give it to the halting problem。So if you can solve halting problem。

 then you can actually prove math conjectures。It will be solution will be automated。

And so it is not surprising anymore that halting problem is actually。Unsolvable。Right so。

So this seems。Incredibly hard。the solution of all math questions cannot be。Automated。

 you would not expect that。So， this problem is called。So， this is。The halting problem， which。Yeah。

 which was this also an orange example one that was a general problem。

So this general problem is called the halting problem。And it is known to be。

It's provably uncomputable。There cannot be an algorithm。Solving this。 So how is such a thing proved。

 right， if you haven't seen this before。You should wonder。

 how can you show that a problem doesn't have。Solution。So， to prove this。V needsza。

Regress definition of computation。Right， so a rigorous definition。

 a mathematical definition is needed because otherwise， you will be， you will be stuck with the。

Microus is sort of some speed。Or a different speed， low speed， high speed。Or the device。

 whether it's a smartphone， it's a laptop or a tablet or whatever。

You don't want to get confused by the。Diversity of。computationalal devices。Right。

 so you want actually a clean。And at the same time， very general。

 most general definition of computing device。Which is mathematically done and。Then， whether。

Horting problem。Whether it can solve the halting problem。Okay， that's the only way you can go about。

Approving the uncomputability。By pinpointing what is。Meant by machines。

 And what is meant by computation。So， this is done on。On a mathematical。Model of a machine。

Which is the tuuring machine。Okay， this is named， as I mentioned before after。Aen tuing。In 1936。

So it was defined almost a century back。Solving the question of what is meant by computation so。Yeah。

 once you recall the definition of tuuring machine and。Once you define that by computation。

 we always means。Problem being solved on this during machine。Once you define it this way。

 then you can talk about complexity。Almost immediately。So， this course。Will deal with。

Various notions of。Complexity of problems。That can be solved on a Ting machine。

Kis will shorten this 2 PM。So problems that are being solved on Turing machine。呃。

Well talk of its complexity in terms of the Ting machine。Execution。Okay， so that get rid of。

All these differences in the speed of computing devices and difference in the computer architecture。

Diffences in the operating system or applications and so on。Okay， this will be。

 this will be the regular rigorous clean。And architecture， independent definition of computation。

So before I get into the definition or before I recap， recapitulate the definition。

Of curing machine and languages and problems。Let me give a quick overview of the course。So。

 let us quickly。See an outline。So， yeah， so the first is。Discussing the halting problem。

That's not really part of complexity， but I'll do it just to。嗯。Recapitulate important points about。

The tuing machine model and then what can it not solve and how do you show it and the proof the idea of this proof is actually used in other theorems。

That we will do。In this course。Call hierarchy theorems。So halting problem and the like。for example。

 there is this。Hilbert's 10th problem。So this is the problem of。Finding out whether。嗯。A given。

System of equations。Has an integral solution Okay， this is also called the diofenttine。A system。

Whether the Devhenine system is solvable， is there a route。

Is there an algorithm that tells you whether there is a root and if there is a root find it okay so that was asked by Hilbert whether there is such an algorithm。

 he had hoped that there is an algorithm。But then it later not was shown after many decades。

That actually this problem is uncomputable。Okay， halting problem reduces to this。

So here is a very simple to define problem。We are halting problem。

 which is kind of completely unconnected。Relates to okay， we'll discuss that。Then。

Second is a very important problem。So I am actually just going to list the problems and according to the problems。

 new topics come up。You can think of them as major chapters。 So second problem is that of satAT。

Which is short for satisfiability。So what is satisfiability。

 This is probably the most important open problem in computer science it is。Given。😔。

A boolean formula。Fei。In。And or not gates。So， for example。It can be this。X1， or x 2。And x2 bar。

 or x3。RightSo x and x to x3 are literals variables。

And their compliments are also allowed this you achieve by the negation gate。

And then you are ordering them or。Doing an ant。 So either you do disjunction or conjunction。Right。

 so phi in this example is a conjunction of2。Disizjunctions。These disjunctions are called clauses。

 so there are two clauses you are doing an and。Satisfiability question， as the name suggests says。

Whether this formula file is satisfiable。Okay， can you assign xon X32 false values？

Sos that phi becomes true。That is the meaning of satisfiable。So， decide。Whetherer。Fi。😔。

Is satisfiable。Okay， so that is the question of set。That is。Whether there is。An assignment。Xi。

 two falses。Sas that fire is true。So this is where everything starts in complexity theory， actually。

Okay， they have simple problem。On boolean formulas。In fact。

 computers use these gates and are non gates。So it's inspired from there and whether it is formula is satisfiable。

So， this will define the。Most important question in complexity。

 which is or in general computer science。And then finally， also in math。

Whether P is different from Np。Okay， well get to that when we do this chapter， third problem。

We correct the spelling。Third problem is。QBF。Quantified bullolean formula。So。

 quantified quantification means that。You either do for all or they exist。On the variables。

So satisfiability you can think of as。嗯。Using a there exist on all the variables。Right。

 the does there exist x 1 x to x 3。Such that5hi is。True， but now you can also use for all。

 so you can actually mix and match。Its like there exist x1 for all x2。

 there exist x3 says that phi is  true。Right so now we are given quantified Boolean formula。

So given a formula with quantifiers。They exist for all。Again， an example is。Phi equal to。

Did it exist x1。They exist x2 for all x3。The same formula that you had before。Which is x1 or x2。X 2。

 bar， or x 3。Right， so instead of asking whether they exist x1 x to x3。Assignment。

 we are now saying that does there exist assignment for x1 x2？Such that no matter what you fix x3。

 which means true or false。The formula remains true。Right， so。Is it true in this example？

Can you set X1 x 2 so that。Independent of x 3。Both the clauses are true。 So yes， you can do it。

 You can just。You want to， basically。X2 bar， you make it。1， you make it。True， right。

 so you can set x2 to 0。And you can set x 1 to1。And that will make x2 bar to1。

And then x3 doesn't matter。Right， X cant be anything。Since x2 bar is already1， which I mean true。

So both the clauses are two， you formalized too。Okay， so in this case， phi is indeed。住hu。

Maybe I use a different variable。So。That this is the question of computational question of Q B F。

 So decide whether。sai。Is true。And when you study this in that chapter， we will define。

New complex3 D class， and。The question will be。NP different from piece space。

So I'm just telling you the questions。Okay， here the question is whether that P is different from N P。

 whether you can solve that， That's the question of。P not equal to Np。

Whether you can solve QBF we will show that QBF actually can be done in polynomial space。

 so it's in P space。But can you do it faster。Okay， so that is kind of the question of P different from P space or NP different from P space。

Those are the questions， so these are practical questions。

 but out of practical questions we will actually come up with。Complexity classes。Okay。

 will not when you define a complexity class and you ask these questions。

 you are asking a question about。Infinitely many problems instead of just one problem。Okay， that is。

Kind of the interesting thing。About complexity questions。



![](img/2c117ddb0bd12a7043b09ca966ce6a0b_2.png)