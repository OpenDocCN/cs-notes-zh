# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P11：11_03_03_典型数组处理代码.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/4856c147c28ac186dca4329f70f47cc1_0.png)

Next， let's take a look at some examples where we use arrays to perform some interesting computations。

First one we'll do is a simple one， let's create a deck of cards。

 and then we'll be able to use that as a basis for some interesting computations involving decks of cards。

So to do this we're going to define three arrays， the first one is all the possible ranks that a card could be。

 and they could be the numbers two up through 10 and then Jack Queen King in Ace。

 so this 13 different ranks and we use the literal representation to create that array and then down at the bottom is what the array of ranks looks like。

And then we build another one of length four that gives the suits， clubs， diamonds。

 hearts and spades and then with those two what we're going to do is build our deck。

 which is an array of size 52， and we'll start with an empty array and then for deck and then we'll write the code to fill it in with the 52 cards。

And to do that， we're going to use nested for loops。

So that's what the code looks like and it's got this， it's a nested for for all this possible suits。

 for all the possible ranks， fill in a card with a deck with a card of rank I and suit J。

 So the right hand side is okay and the lefthand side you have to think about a little bit to see what it's doing and we'll take a look at that in a second And I just mentioned we use 4 and 13 because in lecture it's pretty clear that for you to understand that there's four suits in 13 ranks in actual code would probably use rank dot length and suit dot length instead of those specific values and even deck dot length instead of 52。

Okay， so we start with I and J at0 and you can see those up above the suit and rank。

 And then the first thing is I is 0 and j is 0。 so I plus 13 J is 0。 So deck of0 gets the first rank。

 which is two and the first suit， which is clubs， so two of clubs。

Next thing we do is increment I J is still zero， so it's going to be deck1 and that's going to get the three of clubs the rank one and still suits zero。

 so now you can see J stays zero I increments and we go through and fill in the first 13 positions of the array with all the clubs J is zero so we're just getting deck of I。

So now we do the king in the Ace now。When I has reached 13。

 then we're going to increment J and start at I equals0 again， and now we have j equals1。

 so and I is 0 so we're talking about deck 13 and deck 13 gets rank of0 which is the two in suit of1 which is diamonds and so now we'll go through the whole thing。

With diamonds， the value of J stays fixed and the value of I increments。 So essentially。

 we copy the diamonds into deck。So now you can see how this loop works。

This is the entire program and if we run that we get the result that we want I just have to point out I'm sure some of you are wondering in UniIcode you get to use symbols like clubs。

 Diamonds， hearts and spades you don't really get color though that's artistic license for the lecture again just to make it a little easier to read our output。

So that's a complete program that creates a deck of cards。

 and now we can look at some interesting computations that we can perform with decks of cards。

Before we do that， however， just to make sure that everybody is thinking properly about nested loops and index computations on arrays。

 think about what happens if we switch the order of the four loops。So instead of j equals 0 to4。

 i equals 0 to 13， we do i equals 0 to 13， j equals 0 to 4。

And the answer is that the array is going to get filled in in a different order。

 but the output is going to be all the same， so I stays at 0 and we increment J。

 what does that mean that means the next thing is we do I equals 0 and j equals 3 J equals 1。

 so we do deck 13 next。It's still the same card that went in deck 13 before。 But we。

 what we do is we put in all the twos。And then J gets back to0， I goes up to1。

 and now we do put in all the threes。So at this point where J equals 2 and I equals 1。

 So 13 times 2 is 26， and1 is 27。 So we'd filled in 27。 We do all the threes and so forth。

So the answer to the question is the computation has the same result。

 but the stuff goes in in different order， and eventually we get to do the ACEs and then the last one that gets put in actually in both cases is the ACEces spades that gets put in at the end。

So there's that。And I just point this out。 if you have an old printing of the textbook。

 there's an error related to this。Okay， what about we what if we wanted the cards in the deck in a different order now we have them by suit。

 What if we wanted it by rank， So how would you write code to put all the twos then all the threes and then all the fours and like that。

And that's worth thinking about， and here's the solution。We do i equals 0 to 13 j equals0 to 4 again。

 we could switch the order and get in different order。

 but now we say deck of 4 i plus J equals rank of i plus suit J， let's see how that works。So again。

 we start out with the two of clubs。And now when we increment J， we increment J first。

4 I plus J gives us the two of diamonds。 So I stays at 0， and we increment J。

 So we go through all the twos。Then， increment I。And now we do all the threes。那。

And looks very much the same， but it's a different computation。

 It puts the cards in the array by rank， not by suit。Either one is fine。

 as we'll see because the very next thing we're going to do is shuffle the cards。Okay。

 so let's look at picking a random card。And that's a comic relief break。 Okay。

 so let's say what we want to do is print a random sequence of N cards。And our method is going to be。

 we're going to take the value n from the command line and we're to perform the following step n times。

We're going to calculate a random index R between 0 and 51 and then print the card at that position。

And so we'll just use that same program where we printed the deck， but instead of printing the deck。

 what we're going to do is instead of just printing it out， we're going to use math。

random and we looked at this code before at the end of the lecture when we' were talking about data types。

 this code here gives each value between 0 and 51 equally likely， and so then we just printed out。

And this method actually works， it doesn't have to be cards， it can be any array of anything。

 we can randomly choose an element from the array using this method。So that's the code。

 it's the same code as before except it's got that random choice ahead of time。

 so if you want to draw 10 cards， you get a different result every time now remember this sample is with replacement that is you can get the same card twice in this sampling。

And so another interesting problem to look at is what if you wanted it without replacement？

And that's a little more like what you're thinking about probably。

 which is how do you simulate shuffling and dealing from a deck of cards。

 so what we want to do is I want to have a shuffled deck and I want to deal out a hand of an cards。

And so our algorithm is going to be shuffle the deck and then deal。

 we do more complicated things in a game when we want to do multiple hands and so forth。

 but let's start with the simple and shuffle and then deal。

So here's an unaffective algorithm for shuffling。We're going to consider each card index from  zero to 51。

We're going to calculate a random index between I and 51 and we're going to exchange deck I with that one。

 so we're going to move through the deck and for every card we're going to find a random position further on to exchange that one with and then move on and then we'll print the first end cards in the deck and that's a way to get random cards without replacement。

And that's the whole code for it for I from0 to 52 so that's every card in the deck we compute an integer R that's between I and 51 so that's slightly modifying that code that we did this one gives a random integer in the range from I plus1 to 51 and you can check that and then we exchange the card at position R with the one at position I and then we just print out n of them let's do a trace of that computation to be sure that we appreciate how it works we'll just do it for 10 cards and they're all clubs so we start I equals zero and we generate a random position R in this case it comes out to be7 and then exchange the two of clubs with a card at that position which was the nine of clubs。

And then p equals 1， it's R equals 3， and we exchange it three with the5。And equals  two。

 it turns out to be nine， so we changed the four with the jack。And so forth。

Each time exchanging the card at position I with the card， the randomly generated position。

And at the end， there's really nothing to do。So it looks randomly ordered at the end。

 this is the order along the diagonal here and it's worth thinking about why this method works。

 it's not obvious， there's other methods that you might think about and people implement other methods that don't really work。

 and this is not a complete proof， but at least I think I can convince you that it works all right。

So the thing first thing is it only uses exchanges within the deck。

 so you know that the deck after the shuffle has the same cards as before， that's important。

 you could write code that winds up having 13 to a clubs in it and you might not know if you didn't do a trace。

So the other thing is that the way we wrote the code。

 the card at position I has n minus I equally likely values。

So that means if we go through the entire deck， we start with the first one has n equally likely values。

 the next one， n minus-1 and so forth， multiply those out。 You get n factorial。

 equally likely values for the whole deck。And it doesn't matter what the initial order is。

 and there's in factorial different ways to arrange and cards。

 so that should convince you that this method is effective。And again。

 this could be any type of data in any array， you run the same method and you're going to get it shuffled。

And then what we did in our one application was just so we shuffle and then deal。

 so if you want a poker hand， you do five， if you want a bridge hand。

 you do 13 and you're not going to get duplicates there because we made sure that what we did was shuffle the deck and then pick out the cards that we want and if you want to deal out four bridge hands you could adjust this code appropriately or however many poker hands。

So this is the basis for writing programs to process deck of cards if you wanted to calculate the probability that you get a full house。

 you could use a simulation like this to get started and there's lots of other things that you might want to do。

We're going to look at more basic mathematical problem called the coupon collector problem。

This is a classical problem， as we'll see。 and it's very simple to explain。

 So you've got coupons that。You might get from some source maybe baseball cards or magic cards or we'll do it in terms of playing cards and you get them randomly each type of coupon equally likely and what you want to do is collect all different types you want to have one of each of the different types and the question is how many coupons do you need to get the full collection like for example。

 let's say we're looking for we have a random sequence of cards coming through and we want to collect all possible ranks。

So here's our sequence， so nine of clubs is the first thing and so we collect we know we have a nine and then we get a five and then we get an eight and a 10 and after a while we get something that we've already seen like now we've already had a 10 to diamonds。

 now we get a10 of hearts。So that doesn't add to our collection。 Queen does。

 three does nine doesn't add to our collection。 We already had one of those， five dozen't。

 I think we get another nine that doesn't help。 After a while。

 we start to get cards that we've already had much more frequently。 we already had an eight， finally。

 we got a six。 so that's good。 So now we're looking for a four， a jack or a king。 nope。

 there's a king， that's good。 So now we're just looking for a four or a jack。Again， another 10。

 This is sampling without replacement with replacement。 by the way。

 we're just taking random cards so we can get to tens of heart。We get another ace， there's our force。

 so now we're waiting till we get a jack and luckily we got one right away。So in this case。

 in order to get one of each of the 13 different values， we had to look at 22 cards。

So then the question is if we get random cards， random coupons， we get a random sequence of cards。

 how were going to have how long we have to wait to get a full collection。

So we can use an array to study this problem。And so what we're going to do is， well。

 we'll just number our coupons from 0 to m minus1， and then we're going to generate random in values between 0 and m minus1。

 and what we want to do is count the number used to generate each value at least once。

The key to the implementation is going to be a boolean array that's an array of variables of tight Boolean they're either true or false and Java initializes a mo to false and whenever we get a value R。

 a new coupon then we're going to check the art value in the array。

 if it's true that means we already saw it so we're going to ignore it if it's false it means we have a new distinct value and so then we're going to set it to true and then we're going to count the cards as we go so this is the code to implement the coupon collector problem。

We'll take our number of coupons M from the command line。And we'll start having collected zero cards。

And we'll also keep track of the number of different cards， distinct cards that we've seen。

But we're not keeping track of anything else for every value。

 we're just keeping track of have we seen it before or not So we started out saying no。

 we haven't seen anything they're all false as long as the number of values that we have is less than M we're going to keep going we're going to keep going until we get all M different values and so what do we keep going we're going to generate a new card so that's a random value between0 and M minus1 we're going to count it that's the number of cards that we've generated then we're going to check to see if we've seen it before so not found means that we haven't seen it before。

So that means we have a new different value， so we're going to count that and keep track of it。

 and then we're going to set the entry in the found array according to that to be true so that next time we'll skip it if we've already seen the value。

 we just don't do anything and stay in the while loop。And then at the end。

 we just print out the total number of cards that we've seen。 that's a coupon collector simulation。

Let's take a look if you run it save for 13， you can see that you get a a bunch of different values so we're going to have to run it a lot of times and take an average to try to answer the question of what's the average number of cards you expect to do but before we do that let's look at a trace so this is for m equals6 so we start out with we haven't seen anything everything zero first card comes in。

 that's a two。 we look at found of two that's false so we make it true and that's a card and it's a new distinct value。

And we get a zero again， we increment both of them， a four。

 we set the corresponding entry to true and that's a new value we get another zero and so we check the entry at zero and that's true so not found as false so we skip it and just increment the number of cards。

 one we increment them both two， we've seen two before so we just increment cards。5 is new。

 We increment both。 and now we're looking for a three。And finally， we get a three。

 and we've seen 10 cards， and we have six distinct values once we， that's M equals 6。

 And so then we break out of the wild loopop。So that's the code for the coupon collector problem。

Now this is a classical problem dates back to the 18th， 19th century and as I mentioned before。

 mathematicians when probability was coming into existence for very interested in games of chance and so it's actually been known for a couple of centuries that the number of cards that you need to generate to get all M is about M natural log n plus 0。

57721 m about that， and so we can calculate what this expected weight is for various situations。

 like the one we did with suits you expect to do about eight。If you want to do the ranks。

 you're going to expect to do about 41 according to this formula。

If you want to collect all of the 1200 baseball cards that were published in a certain year。

 you're going to have to get 9000 of them before you get them all and if you want to do all 12。

534 magic cards that were existence at a certain point， you're going to have to get about 125。

000 of them。And now we can test these by running our coupon program and we actually do pretty well the computer simulation can really help us validate mathematical analysis and it can also validate software behavior a little bit。

 but we have to do more than than one run， and sos so for example。

 this is actually a famous test for whether a sequence of numbers is got the same properties as a random sequence of numbers it better satisfy this formula to get all possible values。

So once we have the simulation debugged and working。

 then we can run it a lot of times just like we did for gambler's ruin， remember for gambler's ruin。

 we got it working once but then we put in a loop and ran it for a long number of trials and then compute the average over the trials so we can do that same thing for coupon collector put that code inside a loop where we run it for a large number of trials and then print out the average cards over trials。

Now that's a huge computation with the loops， and we're performing lots and lots of random numbers in coupon collection experiments。

But we can take a look at this question， what is the expected number of coupons needed to acquire full collection？

And again from Laplace， we have these ideas from mathematical analysis。

 but running that program on the previous slide， we can run it I guess a million times。

And we get values that are extremely close to what Laplace's formula predicts。

And this is an interesting computation made possible by arrays。

 and it helps us validate a scientific hypothesis。 Is this analysis correct， looks pretty good。

 and as far as this test goes， looks like mat random simulates a randomness。

 Actually Matt there's other tests that math。trandom doesn't do quite so well on but this one we have the ability to at least validate this hypothesis。

 interesting computation made possible by arrays。

![](img/4856c147c28ac186dca4329f70f47cc1_2.png)

![](img/4856c147c28ac186dca4329f70f47cc1_3.png)