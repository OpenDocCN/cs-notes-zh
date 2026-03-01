# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p51 21_04_01_扑克项目介绍.zh_en -BV1Kp42117vh_p51-

![](img/ef22ef425b9f5717c3b841d5873ef324_0.png)

And here's the flop。Those two spades impossible inside straight draw really helped Genevieve。

 with no help for true。Her odds went 32% to 55%。True his bet。And Genevieve called。 Here's the turn。

The king of spades。Drew now has three kings， and Genevie has a strait。Drew needs a king， Jack，9。

 or a red tent， giving him only a 21% chance here。Hit me。

How what was that for the peanut butter and jelly video。 and besides， this is poker， not blackja。

Are you betting or checking。 I really wish I could see those probabilities that they put over there in their corner of the screen。

 Well， that would take all the fun out of the game， wouldn't it， Yeah， probably， but hey， you know。

 it would make a great project for our Courra learners。 It better not be teaching you to play poker。

 No， no， no， they could write a program that reason a description of the poker hands and does a Monte Carlo simulation to determine the odds of each hand winning。

😊。

![](img/ef22ef425b9f5717c3b841d5873ef324_2.png)

Gvieve and I are playing poker， and you all can see the odds of each of us winning the hand based on what cards we each have。

 How does this get calculated when there is only one unknown card。

 you could pretty reasonably work it out by hand。 But if there were many unknown cards。

 it could get complicated quickly， Wouldn't it be great to write a program that could figure this out for us。

 But's what you are going to do with part of the project at the end of each course。😊，To do this。

 we'll need to describe the hands in a way that is easy for the computer to work with。

 Here' is the poker table， from my perspective。In this variant of poker。

 which is called Texas Holham， these seven cards are my hand。 If you don't know how to play poker。

 that's okay。 We'll explain the rules you need to implement this program。

 When all the cards are played， I'll pick the best five of my seven cards and say what poker hand they make。

 At the moment， I have three kings。We can represent this in a way that is easy to work with by describing each card with two letters。

 One for the rank and one for the suit Here， I have described my two pocket cards。

 the ones that are just mine with K H for the King of hearts and K， C for the King of clubs。

 I've described the known common cards Similarlyly。

 The first three are called the flop and the fourth one is called the turn。 The fifth card。

 which is called the river is unknown。 So I've represented it with a question mark and a number。

 In this case，2。 Every that question mark 2 appears in this hand description。

 will be the same card which will be different from question mark 0 and question mark 1。

Gvieve's hand is made up of these seven cards。 her two pocket cards and the five common cards in the middle。

 since I don't know what her pocket cards are， I've represented them with question mark 0 and one。

 She also has the same description of the flop and turn since we share those and also has question mark2 for the river since we will share that card once it's dealt。

 You'll learn how to read input from files， as well as how to dynamically allocate the memory to hold any number of hands that your program is working with in course 4。

 Until then we provide some compiled object files that will read the input for you。

We can use this idea to describe other situations。 Here are our hands before the flop is dealt。

 I know my two pocket cards， but no others。 Quetion mark 2 through 6 represent the common cards。

 which are as yet unknown， but will be the same in both hands。 However。

 for the spectators and announcers， all the pocket cards are known。

 having more information gives you a different calculation of the probabilities of the hands。

 Genvieve's hand is actually really good， So her odds of winning are better。

 given what her hand actually is than if we assume it is a random hand。

Our input representation is flexible enough that we can represent many other common poker variations。

 For example，7 card stud has no shared cards and some that are dealt face down and some dealt face up。

So that's how we'll describe the situation in a poker hand。

 but how will you actually go about calculating the odds you could make your program consider every possible combination of cards if you have four known cards and five unknown cards as would be the case if we can see two players hands and have five cards yet to deal you would end up with about 205 million combinations。

 that's not so bad as computers go， we could do it in a matter of minutes。

 but we'd like to be faster than that。Could we work out the formulas for every case based on the principles of probability and combinatorics。

 maybe， but that would be a lot of work， especially given how many cases there are and how much these depend on what other cards each other player has。

Instead， what we are going to do is a Monte Carlo simulation。 So what is a Monte Carlo simulation。

 you will draw a large number of random hands for the unknown cards and see who wins and count up how many times each of players wins the hand and use those numbers as estimates for the probability of each player winning。



![](img/ef22ef425b9f5717c3b841d5873ef324_4.png)

If you do this for a large enough number of random draws， your answer will be very accurate。

100000 random draws is pretty fast and gives estimates that are quite good。

 The idea of Monte Carlo simulation is not just limited to poker or card games。

 but is a broadly applicable technique whenever determining the exact answer is incredibly complicated or computationally difficult。

 Let's head back to our poker game and see how it finishes。😊，And here's the river。10 of spades。 Wow。

 Genevieve drew the straight flush， but Drew probably thinks his hand is good with a full house。

All in。Call。Full house。Straight flesh。And Genevieve wins the $25 million pot。 What a game。



![](img/ef22ef425b9f5717c3b841d5873ef324_6.png)

Did I say million， I meant 25。

![](img/ef22ef425b9f5717c3b841d5873ef324_8.png)