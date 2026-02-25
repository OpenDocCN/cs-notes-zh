# UCB《计算之美与乐趣｜CS 10. The Beauty and Joy of Computing 2022 spring》中英字幕 p12 CS10 Lecture 12 (Mar 2)_ Recursion II- Count Change.zh_en -BV1BokLBmEKE_p12-

嗯。

![](img/26ff02d7db4e57e2fd05eef0917bf429_1.png)

![](img/26ff02d7db4e57e2fd05eef0917bf429_2.png)

![](img/26ff02d7db4e57e2fd05eef0917bf429_3.png)

![](img/26ff02d7db4e57e2fd05eef0917bf429_4.png)

![](img/26ff02d7db4e57e2fd05eef0917bf429_5.png)

![](img/26ff02d7db4e57e2fd05eef0917bf429_6.png)

![](img/26ff02d7db4e57e2fd05eef0917bf429_7.png)

Can someone put something in the chat if you can hear me on Zoom？系。Okay， cool， thank you。

 sorry for the late start I'm。😊，Cool thank you so much Okay hi everyone I am going to be doing lecture today if you haven't met me before my name is Beaksha。

 I'm the discussion TA for CS10 and yeah Michael is on vacation or he's at a conference so I'm going to be covering for today。

😊，嗯。

![](img/26ff02d7db4e57e2fd05eef0917bf429_9.png)

嗯。😊，对。

![](img/26ff02d7db4e57e2fd05eef0917bf429_11.png)

Okay。So today， we're going to be。Covering recursion too so you did recursion last Wednesday I think Michael went over some but I'm going to do a bit of a review on that and do a couple examples and then we're going to be doing something called tree recursion which is basically when you have multiple recursive calls within the same function and then we're going to talk a little bit about why we're learning recursion and then we're also going to do some factors which is some it's like a visualization of recursion and you might have already seen it in lab but you'll see it this week and this is also usually what we do on the midterm for the in lab midterm。

😊，Okay。So。Just some announcements to start out with。

 hopefully you've seen I think Madty posted yesterday that the project one deadline has been extended by one day。

 so it's now going to be due tomorrow at 1159 pm and yeah so hopefully that gives you a little more time and then I think there's a work session in lab today and as well as tomorrow if you're in a Thursday lab so hopefully we can get some help on that if you're still working on it the only thing is midterm is coming up on March 14th。

😊，So yeah， it's a little while out but just so it's on your radar。

 more details about that will come in the coming weeks or in the coming days。

And we'll also be posting some study resources that you can use to prepare for that and then lastly the Exp post assignment is going to come out later this week after 2048 is due the Exp post is kind of a more chill assignment than the other ones that you've probably donesify it's kind of just a chance for you to explore an area of interest and just right of short paper about it and that's going to do next Wednesday and then you're going to comment on others by Friday。

 but that'll come out either tomorrow or Friday I think any questions about logistics。😊，Cool。

 I'm gonna keep going， then。How do you how are you guys feeling about recursion。

 do you feel good about it or do you want to kind of review？はい。With you。So yeah。

 I'm going to go over the basics of recursion to start out with， so just as Hannah move this。

SoAs a reminder what is recursion so recursion is the repeated application of any of a recursive process so if you notice when we're defining recursion we have the word recursive in it itself and that's because that is exactly what recursion is recursion is when you use the function that you're defining within the function itself so using Sap we're defining block so it's like you're writing code but block you're coding how to how to do how to solve some problem using a block and inside of that block definition you use that block that you're writing so that sounds kind of weird because it's like you haven't written that block yet how does it work but that's like the beauty of recursion and so yeah we'll talk about that but basically the idea is that you're able to use simpler subproblems to solve a larger problem so when you make this recursive call when you use the the block that you're defining within its definition you're always calling it on a smaller subproble and then you kind of want to combine those sub problemsm in a way that you can answer your main question that you're trying to code with this block。

😊，So recursion is usually useful when there's some sort of pattern in the problem that we're trying to solve since recursion is kind of repeatedly applying the same process to smaller inputs yeah so that is basically what recursion is and then there's two main cases in recursion we have the base case and the recursive case and I'll talk a little bit more about the differences between those in a second but the recursive case there's kind of three steps that you can think about when you're doing the recursive case there's a split step and invoke step and a combined step。

😊，So those are the basic， let me keep going。So so for the base case。

 the base case is always gonna be the simplest case of your problem so sometimes this is like an empty list or your input has a length of zero something like that so it's the simplest case of your problem or you're trying to think of your base case you want to think of what is a version of this problem that I can solve without doing any like any additional computation like what is the easiest version of this problem so like for example if you're trying to find the length of like a list or something the easiest or sorry if you're trying to like add all the numbers in a list the easiest the easiest case would be if the list is empty right because if the list is empty then sum of all the values you can just return zero or if the list has one value sometimes you could use that as your base case if the list has only one value you don't have to do any computation you can just return that value but if your list is longer than one value。

 then you might want to do some recursion because you can use some problems to do that such as like an example but this base case is basically our stopping point so any any function call that you make。

😊，Your block is always going to eventually hit this recursive case because the recursive cases sorry the base case the base case is the only place where you're actually returning something without making another recursive call and so if you are trying to make some if you write your code and you make some call to your block without having it hit the recursive case then your block is going to end up just running infinitely and you're gonna get an error it's just going like maybe you highlight in blue and staff and it's just going keep running forever and it's not gonna to ever stop because you never hit the base case which is where you're actually returning or reporting so all recursive calls because of that need to be working towards the base case so what that means is like I mentioned earlier a recursive cases are smaller subproble right so our inputs to our recursive case have to be working towards the base case and that they should be getting smaller so that with each recursive call you're getting closer to your base case Another thing to note is that you can have you're allowed to have multiple base cases and usually as you get to more complicated problems you sometimes need a multiple。

Base cases maybe because you have multiple inputs to your blocks you need a base case for each input or maybe because you have only one input but maybe you need to handle like an odd case in an even case you want to return something different in those two cases so because of that you might have multiple base cases and yeah and then mostlyly just some common inputs I already mentioned this but if you have like an empty list like zero input value zero if you're really stuck and don't know what to think about for what the base case should be you can always kind of start with that if your input is a list or if it's a number any questions about the base cases。

😊，哇。Yeah。Yeah yeah， good question。 Yeah， so yeah， that was a little confusing So let me clarify so actually it depends on your implementation of the code。

 So what I meant was you could code it in a way that the base case is is like when the length is zero。

 but you can also code it in a way that the base case is length one and that depends on the problem but like if the code that you're writing。

 if you know that your list is never gonna be like length0。

 then you can just use length one is your base case and have it recured down to that point but if for some reason when you're doing your subprom。

 you're like removing more than one item from the list at a time so there might be a case where it hits zero then you might want to use that for your base case it's usually safe this to just use zero because if then that way if it does hit zero then you have it covered。

 but sometimes you can think about and I'll show that in a second with factorial that you can you can just do it with one that sense。

😊，要死。O。Okay so for the recursive case I kind of talked about this as I was talking about the base case。

 but the recursive case is anything that's not covered by the base case so you do your base case for your simplest input and then everything else is covered by your by by the recursive case and so that's going to always kind of be in like the else of your of your if else block in your recursive definition and this is where you actually make the recursive call to the function that we're defining so this is where you actually do the。

😊，You put the block that you're defining in this step exactly。Again。

 like I mentioned with the base case， we always want to be reducing your input in some ways so that you're working backwards too is that base case。

 so you're maybe making the number smaller reducing it by one each time or maybe you're removing one item in your list each time so and staff that usually comes down to using like all but first something like that。

So you always want to be working towards your base case so that we don't end up in infinite recursion where our block is just running forever and it's usually like this isn't like always true but just a note is that it's usually like the last line in your code it's going to be in the else case because this is the recursive case is what you want to do if if you don't if you don't have a base case in any other situation you just want to do a recursive case because it'll kind of make your process easier makes your code cleaner because you don't need to handle each individual case and then lastly another thing is that it's possible to have multiple recursive calls so like I mentioned that you can have multiple base cases。

 having multiple base cases usually isn't like that difficult once you figure out that you might need multiple base cases but sometimes having multiple recursive calls is confusing because you're like calling the recursion multiple times and combining the result of that so that's mainly what we're going to talk about today but it's possible to have multiple recursive calls within one function and this is what we call tree recursion is just like what we call it。

And a common example of this is facttals， which I kind of mentioned。

 have you guys seen fractals in lab？Yeah， no a little bit。

 I think it just was last week so it's probably do this upcoming week but yeah so I will talk about those but yeah。

 that's like a calm example and yeah the main thing with the recursive cases is you always want to be thinking about how you can break down your problem into smaller subproblems and you might have heard this somewhere sometimes like staff uses this term of the recursive loop of faith and if you take 61 a they I'll talk about this a lot too and what the recursive leap of faith is is you want to take this leap of faith and assume that your function can solve smaller versions of the problem that you have so again I know I'm kind of repeating myself a little bit but I really want to emphasize that it's really important to like assume that your block will work on smaller inputs and that since that kind of feels like wrong because you haven't finished writing the block yet。

 that's why we call it like a leap of faith you want to take the leap of faith and assume that it's gonna to work on smaller inputs but obviously like the rest of the block has to be implemented correctly in order for it to actually work but you want to take that leap of faith when。

Wt your code and then you can work backwards from there if you need to debug it any questions about the recursive case？

Okay。😊，Moving on and。So really quickly I just want to talk about some steps that I like to think about when writing a recursive function so if you're given a problem and you want to you need you're asked to solve it using recursion I think the first step I mean this isn't like that you have to use that this is what I recommend is think of the base case first so think of the simplest case and then use that as the base case so what is the simplest case of your problem so again like I mentioned it can be like if your list is empty if your number is zero if your number is one maybe but your simplest case。

 what is a case that you can do without doing any additional computation and the next step is you want to think about how you can use smaller a smaller version or multiple smaller versions of the problem that you're trying to code。

😊，And use those to solve the main problem so this kind of can be broken down into three steps or three concepts。

 so there's the split step。 This is the actual splitting of the problem into either one subprom and like the smaller simple case or just a couple subproblem and then you want to invoke that's just where you actually make the recursive call so that's just when we call that block on the subproblem with a smaller input and then combine you want to combine those results together to get the final result So those are just some steps but I think it makes more sense with an example So let me show this you probably if you went to discussion this week you've probably already seen this but I wanted to go over again because I think it's a really good example of recursion and if you're confused about the concept of recursion I think it does really good job of showing that so first just as an intro factorial is a function that's denot by an excavation point you've probably seen it in some classes but basically it's defined as the product of all natural numbers less than or equal to a given number so we can this definition out like in this blue box where we have n factorial。

😊，Exlamation point is equal to n times n minus1 times n minus2 and so on until we get to one right so it's the product of those numbers And so something that we can notice is that if we wanted to write down the definition for or write out what n minus-1 factorial would be it would be n1 times n minus2 times n minus3 and all the way down to one right but something to notice is that this noticing that we can write n1 factorial like this following by the definition。

 we can actually rewrite the definition of n factorial in terms of n-1 factorial so n factorial can be equal to you can say that that's equal to n times n minus1 factorial and now you can notice that we've actually created a recursive definition for n factorial we haven't written that you code yet but this definition in itself is recursive because we're saying that n factorial is equal to n times n minus1 factorial。

 so we're using the definition of factorial when defining the factor。😊，What a factor is for a number。

 Does that make sense， So this should hopefully provide some intuition for why we might want to use recursion in this in this problem。

 why we might want to use recursion to code a factal block。

 because even in the mathematical definition， we can kind of see how it is recursive in nature But before I move on I just want to make sure does anyone have any questions about do you want me to go over it again about why n factial is equal to n times M minus factor。

真。Okay。Okay， I going keep going then。So for the bacterialial example it's just so we our goal is that we're trying to write a block that computes n factor given an integer end right so going through our steps that I showed earlier。

 the first step is we want to think of the simplest case to use as the base case so can anyone tell me what the simplest case for a factorial might be。

😡，Yeah。Yeah， exactly exactly one。 And so we can say if n equals one。

 then we don't require any computation right we can just report one right away。 So yeah。

 exactly thank you。 So the simplest case that we can use is just one。

 So that's gonna to be a base case and then the step two。

 we want to think about how you can use a smaller version of the problem to solve the main one。

 So we kind of already talked about this when I was showing the definition So let's just go into it。

 so we want to split the problem into a subproblem that can be solved recursively and a simple case。

 So we can split our problem into n and n minus one factorial right because we just define that n factorial is actually just equal to these two multipied together。

 So we split our problem into a subproblem of minus1 factorial and subproblem just means like a smaller problem a smaller instance of the same problem and then n is just a separate a simple case。

 And so we've split our problem and then now we need to invoke the recursive call。

 So that just means that we call n minus one factorial。 So what that means in snap is you maybe。😊。

Have to click apply to get the block to appear and you drag in your factorial block and pass in n-1 as input to it。

 So that's the recursive call part。 That's the invoking part。 And then lastly。

 we want to combine the pieces from the split step to get the final result And that's going happen by multiplying right because that's how we defined n factorial。

 we want to multiply n times n -1 factorial。 So our final result is in our else case in our recursive case。

 we're gonna do if sorry， in our else case， we're gonna just report n times the factorial of n -1 Any questions about these steps。

Okay。So this is what it looks like in code again， probably I've already seen this but I just want to make sure that it's clear because I think it was still confusing in discussion for some people why this works so we have our factorial block。

 this is our base case if n equals one report one else just report n times factorial of n minus1 and something to know just like something I like to or this helping when I was in CS10 is you can kind of just imagine like when you make your recursive calls just pretend like you have this help or block that is able to perform the action of whatever block you're writing on any smaller input just forget about the fact that it happens to be the same block that you're writing just imagine that you have this extra helper block and what would you be able to how would you be able to solve the problem if you already know that you have a way to solve a smaller problem and just use that block taking that recursive leap of faith again。

Is say pretend Ken that's already。Yes， yeah， exactly。

 it's like you're taking a leap of faith and assuming that it's going to work。 other questions？Yeah。

You kind of think of blank。Yeah， exactly。 Yeah， that's how that's how I like to think about it。

 It is like obviously it is the same block， but it functions as just another block because snap doesn't really。

 I mean S like it does know I guess that it's the same block but S doesn't do anything different knowing that it's the same block S is just going go and it's going to go into this else case and I'm going walk through an example of this。

 but it's going to just go into the else case if n iss not one and it's just going to do n times factorial of n-1 and it'll see factorial of n -1 and it'll say oh。

 that's just a custom block So let me look at the definition for factorial of n1 and it's just going go in there and continue。

 So S doesn't really do anything different at all if it happens to be a recursive call yeah。对就是。Yeah。

 good question。 Yes you can definitely implement it in other languages。

 I think almost any language supports yourcursion。 so yeah， good question。Anything else？Okay。

 so would it be helpful to like walk through just a really small example of bacterialial three to see why it actually works？

Go through it， but if it is if you guys think it makes sense and I can go through quickly but okay sorry I'm know to put these zoom things are they on the screen okay。

 so let's just say we're trying to make a call to factorial of three right so three factorial what does that just report or what should we expected to report？

😊，It's just going to be like three times two times one right so three so factorial three it should report six。

 everyone clear on that。Okay cool so what's going to happen is we make this call to factorial of three。

 we have this function definition so now n is three in this case right n equals  three because that's our input so S is going to look in here and it'll see if n equals1 and n is not equal to1 because n is equal to3 so it's going to go into our else case so now it goes into the else case in the L case it sees oh I just have to report n times factorial n minus1 whatever factorial of n minus1 is so it makes the call to factorial of n minus1 again n is3 so it's factorial of 2 and then factorial so then snap goes oh I need to now make the function call to factorial of2 so now that goes into the function definition again and it sees if n equals1 and again now n is equal to2 so it's still not one so it's going to go into the L case and then this is going have this is going call report it's going to report two times factorial of1 right because2 minus1 is1 and we're just making a call to n minus1 in factorial so。

😊，Now we have two times factorial， so we had factorial of three。

 which tried to report three times factorial of two， but then to get factorial of two。

 we have to do two times factorial of one。 I that clear so far。😡，Okay。

 and then what happens is factorial of one is now going to be called right， And so now n is one。

 So when we go into the function definition， we see and if n equals one。 So now snap knows， oh。

 I need to just go inside of here。 So this is gonna to report one。 Just this part。

 The factorial of one is just one， because if n equals one， we just report one。😡。

And now what happens is now we figured out that this is one。

 So now S is going to finish this little box here。 it's going to do two times one because factorial of one was one and it was the reason that we have this box is because this box is equal to factorial of two so it's gonna to get two and then it's going to pass that back up into factorial of two because factorial of two made this call to two times factorial one So now we have three times two for factorial of two and now three times two is going to be6 right because factorial of two evaluated to two because of this box here and so now this whole box three times two is going evaluate to6 and the reason that we have this box is because factorial of three was supposed to be equal to three times factorial of two So this finally we're going to end up with reporting six as our final answer because it's going to be passed back up if that makes sense。

Yes。Sounds good any questions seems like people are understanding so I'm going to move on。😊。

So now we're gonna move on to like a whole different problem this problem is called count change and this is a tree recursion problem that I had started talking about a little bit earlier sorry moving so count change is a tree recursion problem which means that we just are going to have multiple recursive calls inside our problem other than that it's like the same concept of taking that recursive like the faith and assuming that it will work and breaking down a problem into subprom but something I want to mention like I've been mentioning is that it's really really important in tree recursion especially and in this example to trust that recursion and assuming that it'll work on smaller inputs because with factorial I just kind of drew it out or had it on the slides and it was kind of clear to see like oh this is making this function call this is making another function call and it's kind of clear to see how it actually works but as you get to more complicated recursion blocks you won't be able to do that because they're just going to get really complicated and that's why we're using recursion in the first place because it kind of simplifies that process it's kind of like abstraction。

obbsstructing away how to solve the smaller sub problems by just using the recursive definition。

 so we're going to kind of do that thing where you pretend that there's a helper function that works on smaller inputs。

😡，So that's just an intro to that。 so now I'm going to go over。

What this block sorry let me put this here Okay now I'm gonna go over what this block actually what we're trying to do with this block。

 So feel free to stop me at any time if it doesn't make sense。

 So what our problem that we're trying to solve with this count change block is we want to know how many different ways can we make change for an amount of money using a specific set of coins So our block has two inputs right it has a number input。

 which is this first input and this input represents the amount of money that we want to make change for。

 So our block is reporting the amount of the different number。

 the number of different ways that we can make change for a certain amount right so that's what this input is。

 and then this is gonna to be a list input and that's going to take in the list of coin deminations that can be used。

 So for example， like in the US if we have like quarters。

 we have the standard set of coins a quarter dying nickel penny that's like here this would be a list of like 25105 and one for how many cents each of those are。

 So this amount is to be in the same units as what。I have a coin denomination we list here。

 I'll show some examples if this is confusing， but that's like the main idea of this block and it's going to report that integer which is the number of distinct ways that change can be made using the given set of coins and then one more thing to note is that we can assume that we have an unlimited amount of each type of coin。

😡，So let me just show some examples so to start with for all these examples we're just going to use like the syned US set of coins if you're not familiar with it we have 25 cents coin 10 cent coin a 5 cent coin and a1 cent coin so this is what would be passed in as input to this list it would be a list of these four numbers so if we wanted to know how many different ways that are to count change for5 cents right there's two ways that we can count change for5 cents we can either use one nickel so one of these five or we can use five pennies right and those are the only two ways there's no other way to actually get exactly5 cents using these specific set of coins so our block should report two like this does that make sense。

Yes， okay， so another example， if we have 10 cents， there's four ways that we can make 10 sets。

 we can use one dime we could use two nickels， we can use a nickel and five pennies or we can use 10 pennies so this block is going to return report four in that case and then sorry this is in the way a lot。

😊，But lastly， if we have 15 cents there's six ways that we can make change for 15 cents we can I mean I'm not going to read them all out。

 but basically you can use one dome one nickel so like a 10 cent5 cent。

 one dime and five pennies so a 10 cent and then 51 cents and so on so there's six total ways and you can kind of do it out and see on your own that there's exactly six ways that you can exchange change for 15 cents。

But this can get really complicated to just like write out and like think of on your own like how many different ways we can make change for some number of sense。

 especially as the numbers get really big。 like there's so many different ways you can do。

 especially with pennies。 So because of that， we're gonna kind of use recursion to solve smaller sub problems and help us make this。

 So that is that's what this block is doing。 Does anyone does everyone understand like what count change is doing if you have any questions。

 let me know。唔山。Okay。Okay， hopefully it's clear so yeah so now let's try to code the block so this is how we have our setup we have account change for amount using coins so this is our input this is our definition right so what is the first step when we do recursion can anyone tell me。

😊，Base case yeah， exactly thank you and so we're gonna set up oh sorry already put that but we're gonna were gonna have a base case that's going to be like in an if statement right and I'll tell you here that we actually have two base cases in this scenario and the reason for that this isn't always the case but I kind of a clue for why you might need two base cases is because we do have two inputs right so it's likely that we need to cut down both inputs so we can kind of use that to tell maybe we might need two base cases so does anyone have any ideas I kind of put but does anyone have ideas for what the base case might be here。

😊，Number one of these is a list， so what is a common base case for lists？

Yeah exactly so an empty list is going to be one of our base cases and then we have an amount so let me just show this I'm just actually going to put both so we actually these are like these are two separate base cases so one base case。

😡，And this kind of in itself is it's kind of like three days cases because these are separate things。

 but if the amount is less than zero or if the list of coins is empty both of those cases we want to report zero and especially this one kind seems weird maybe like why would you have a negative amount but the reason you might have a negative amount might be become more clear when we do the recursive case because as you recurse down your amount might they're not accidentally that your amount might become negative for reason that I'll show in a second but just think about like a like in a simple or sorry like a simple case is if your amount is negative or if you don't hurt any coins。

 if your list is empty， that means you don't have any coins so there's no way to make change for any amount or if your amount is negative then there's no way to make change for that because like we're assuming in this problem that your coins are not going to be of a negative amount so because of that we're gonna always report zero in that case because we're not going to be able to。

Make any change for that， does that make sense？Okay。

 and then the second base case is if the amount equals zero。

 so this is also sometimes a little confusing， but basically if the amount of of money that we're trying to make change for is zero。

 there's only one way to make change for that on that way is to just not use any of the coins and that like feels kind of weird but we do need to at some point report one in one of our base cases right because if we're just always reporting zero like I mentioned earlier。

 the base case is what gets hit by。😡，The base case。

 every function call is going to end up somewhere in the base case。

 so if we don't have if both of these are reporting zero。

 then there's no really way for us to be counting up anything and I think this will again become more clear with the recursive case。

 but yeah。😡，They might be reporting the same thing。

 but in well if they were reporting the same thing youd probably just put it in or so that's like what we have here so this kind of is like three base cases with two of them with the same one。

 but we do have to have a one here because otherwise。😡。

This also it also depends on how you do the recursive case， I'll show that in a second， but yeah。

 so we'll come back to that and explain why yeah。That one of your thoughts。到了。

One of your possible coin bottles is nothing。不是他。Yeah。啊啊。关啊。瞓头壁歌。Yeah， yeah。

 you can kind of think of it in that way。But if you're yeah， so yeah， if you if you have。

 but this this case isn't like if so this case， this case only gets hit if the list of coins isn't empty right so there are some coins。

 but the way that you're making change for nothing is by not using any of the coins if it this conscious choice to not use any of those coins。

😡，Right， so it's not really I guess I'd have to think about that a little bit more if you can consider it like a nothing coin。

 but the idea is that there's one way to do it， which is to just not use any of the coins that makes sense kind of。

😡，I'm going to keep going for the sake of time so now we're gonna try to do the recursive case and this is kind of tricky to see up first so I'm just going to put up this example here so if you remember sorry if for're not familiar with the coin denominations of standard US coins but it's like one down one nickel and this is the six ways that we talked about earlier to make 15 cents So I'm just putting that up to kind of see an example but remember that so now we're trying to to code the recursive case right because we did our base cases so how should we split our problem into smaller subproblem Does anyone have any ideas of how we could do that。

It's kind of tricky， so it's okay， but if anyone has an idea， let me know。

Okay I'm going to keep going so looking at this example we can kind of see like so one idea is let's think of how we can split all the possible ways that there would be to make change for an amount of money and to kind of like two separate cases because and maybe those two separate cases or like smaller subpro of our original problem so this kind of takes some intuition to understand like why you might think of that so let me just show this so our idea is we can either when we're making change for an amount of money we can either include the first coin or we don't include the first coin right。

So what that means is whenever we have some amount of money that we're making change for。

 theres there's only like two ways like all of the ways that can be that can make change for some amount of money。

They will have to fit into one of these two categories。

 either they use the first coin or they don't use the first coin， right？😡，三明山。Yes， okay。

 I've seen some can yeah。With the first one he left。

Yeah the first value in the so good question yeah so it's it's not actually relevant whether like a list is sorted or what order is sorted it's just going to be the first value in our list so in this case I think our first value was like a quarter because it was 25 cents so actually what that means is that in this case all of these we're kind of fit into not using the first coin right because we can't use a quarter we can't use 25 cents to make 15 cents。

😡，But yeah， so yes。Any other questions about this idea that we have？

Okay and keep going so remember our idea was we're either going to include the first point or not include the first point and we we know that that's going to cover all cases and I think once I get the rest of the code up I'll make sure that that makes sense but yeah so now we have two cases that we're going to try to code and these are going to be our two subproblem。

😡，Because remember we're making two recursive calls because this is tree recursion so our two our problems are we want to know how to make change for this amount of money while using the first coin so our first coin is going to be used when making this change or we're not going to use the first coin so let me。

😡，So our first one our first case is we use the first coin to make change so this is what our recursive calls that problem looks like and let me just put both up So they're here and then this is if we don't use the first coin to make change so I'm actually going to talk about this bottom case first because I think that it kind of makes more sense or maybe it's more intuitive Can you see that the bottom case yeah。

Okay so this we're not using the first coin to make change right so what that translates to in our recursive call is we just want to call account change brand amount using all but first coins right so if we have a way to if we have this like recursive call then we're kind of assuming that this recursive call is going to tell us。

😡，How many ways there are to make change for the amount of money that was our input without using the first coin because we're just passing in all of the coins except for the first coin summer sense。

So that's what this recursive call is doing and then this top recursive call。

 okay so first any questions about this bottom one。

Does it make sense why it's doing what we said it's doing？有嗯。都是。

Yeah yeah for sure sorry okay so this case that we're trying to code here is we want to know how many different ways are there to make change for the amount of money that not using the first coin so if we just don't pass in the first coin so then we're just passing in the rest of the list everything except the first coin and we're doing that recursively the faith where we assume that this block is going to work then we're able to just make change for if we assume that that works and this should report how many ways there are to make change without using our first coin。

Of yes。啊。Okay。看看。或者很多。对吧。Yeah， yeah， so basically this is just passing in the rest of the coins the dime the nickel the penny and we're going make like multiple recursive calls right because this going go all the way down to the base case until the list is empty so it's going to do this and that's going do like the penny and nickel and then it's going to do just the penny and then it'll be empty so that's how it'll end up but you don't have to think too much about that just because we're going assume that this works right。

😡，Okay， and now I'm gonna talk about this first case。

 which looks a little weird so I'll say a couple times if needed。

 but now we're doing another recursive call remember this is when we do want to use the first coin right so we're making change for some amount of money and we know in this scenario that we are using the first coin in our list whatever that coin in our list is it doesn't matter if it's the largest coin the smallest coin something in the middle we are using whatever the first coin in our list is so we can actually subtract that amount from our total amount when we make a recursive call because we're using we know that we're using that coin right so since we're using that coin we can we if we can count the number of ways to make change for。

So say we're trying to make change for 15 cents right and much much just pretend in this scenario that our coins we didn't pass in the quarter Dme nickel penny。

 we just passed in the dime nickel and penny Okay so our first coin is the dime。

 So if we know if we want to know how many ways there are to make change for 15 cents using using just a nickel and a penny right not using the dime。

 So what we oh I'm sorry not like Oh yeah so so we want to know how many ways there are to make change using the dime So we we know that we're using the dime in this scenario So we can subtract off 10 cents from our total 15 cents because out of a total amount 10 cents is already accounted for because we know that we're using a dime So if we know the number of ways to make change for basically 5 cents using using all of the coins。

 then that would tell us how many ways there are to make change for 15 cents using the dime。

I do it one more time。Or is that clear？Yeah， I don't know。How do you track。about的反 to do it。Yeah。

 so that is something that just happens in the recursion， So we're not keeping track。

 So this concept， which this is a good question， the concept of like keeping track of something is actually something that happens like in iteration So that's something that we do with like four loop and you have like a running like thing So this is recursion remember like another technique for doing that for solving problems and technically we could do this recursively。

 but it would get really complicated to keep track of all the different ways。

 you'd have to and I'll talk about that also a little bit later but we have to keep track of all the different ways that we're making change and whether or not they worked for this amount like that would get really complicated So that's why we kind of put it down Does that answer your question Okay well anything else。

Okay， so。Okay， so what happens now is we combine this together by just reporting。😡。

Some of these and the reason that this works is because we covered both like any any scenario of the number of ways to make change for a set of coins can be can fall into one of these two cases our two cases that we talked about either they include the first coin or they don't include the first coin so like this if we cut down or 15 cents so let's just pretend like we're not worrying about a quarter right now let's pretend our dime is our first coin so using the first coin this gets split into one this is going to be two and then this is going to be four there's four ways to make change without using a dime and there's two ways to make change using a dime and there's no case that like doesn't use a first coin and doesn't not use a first coin like there's no case that's going to fall out of these two situations so that's why we can be confident that if we know the number of ways to make change with the first coin and the number of ways to make change without the first coin。

By adding those two values together， we'll actually get the amount of change that or the amount of sorry。

 then we'll actually get the amount of ways to make change total because we are accounting for both。

😡，For any possible scenario because it has to fall into one of these two cases， some next one。Okay。

Okay， so yeah that's the main idea with this and the like so our assumption based on our oh sorry。

 do you have a question？Yeah， so regardless of。非。看嘛。えかさとしておを。Yes， yes。

 yeah and yeah it's regardless of the amount as long as like your units are matching the coin denominations that you pass in and that's like really complicated to think about like how many like recursive calls are going to happen because each time you make a call to this it makes like multiple recursive calls because it makes like two recursive calls but those make like a lot more so you can't really trace it down it'll get really complicated but yes it does work for anything and so the best way to think about that is just to really trust that these these subprobles are able to be solved by a block because if we implement it correctly the way that recursion works since we're making our input smaller it should work on those inputs and even if we would have like 100 amount of worth of change that worth of money that we're trying to make change for it's always going any way to make change for 100 it going to fall into one of two cases right either it's going to use the first coin in our list or we're not going to use the first coin in our list when counting up the ways so no matter what we're covering all the possible。

Ways that we can make change in these two cases， so that makes sense？Okay。

Okay I'm going to keep going so just some notes about count change this is just like some things to take note of just observe as we were doing this so in the recursive case like I was just saying I think A already said this but we can account for all possible ways to make change if you take the sum of the two value the following two values the number of ways to make change using the first claim and a number of ways to make change without using the first coin because we're always all the different ways to make change are going to fall into one of these two categories so if we if we just add these two values together and if we assume that we have like a little help of block that can help us solve these smaller sub problemsblems and we assume that it works correctly adding them together we'll give us the correct answer that makes sense。

Okay。So both of these values again are actually smaller sub problemsblems of our original problems so I kind of mentioned this quickly but okay so again recursive week of faith assume that we can computeute these values and the reason that they're smaller inputs of our original problem is because we're reducing one of the two inputs in each recursive call so if I go back for a second our two recursive call see this one we reduce the amount right and our base case for amount is either it becomes negative or it's equal to zero and so since we're reducing that amount we are making that amount smaller so we're working towards a base case and this one we don't reduce the amount so this amount is never going to become zero in this case from this recursive call but we are working towards the list of points being empty so as long as it's working towards a base case in some way it's okay。

三零三。Okay， so yeah， basically we're reducing one of the two inputs in these recursive calls。

 so this way we are worked towards is at least one base case each time。

 but of course those recursive calls might be making more recursive calls that are going to work towards other base cases。

 but you don't have to think about that too much， you just want to kind of assume that it works on the smaller sub problems。

😡，嗯。Okay and really quickly I'm going to talk about my like motivation for recursion so recursion like I kind of mentioned a little bit earlier is just one technique for writing function so another technique that we kind of did earlier was iteration which is like four loops or other types of loops and that's another method that we previously learned and either can work they're both equally as powerful but sometimes one will be better and that's why we're talking about recursion because if you can imagine I mentioned this quickly like if we tried to do count change iteratively it would take a really long time like and a lot of memory to go through if if we were trying to for example make change for 100 like we'd have to iterate through all the possible ways that a coins can be used and make and then keep track of whether they added it up to 100 or not and things like that but if we just use recursion we were able to kind of abstract that all away that keeping track part of it and that just happens with the recursive calls so that's why recursion is helpful and recursion helps us abstract away the problem of iting through every possibility through the use of sub problem。

and recursive calls and then yes those I kind of mentioned so iterative factorial would be easier to implement than iterative count change because we only have like one input and we can just iterate through like all the numbers from one to n if we're doing n factorial and just keep track of multiplying them together so that's not as hard but it does make a simpler solution if we do it with recursion but for count change it would be really really difficult to do it iteratively so that's why we kind of introduce it with a simpler case of factorial but then we want to show you that it really is important。

😡，Because there's so many combinations and then。Now。

 the sooner you're able I know I said this a lot of times but the sooner you're able to trust that the recursive calls will work。

 the easier it will be you come to solve recursive recursion problems and you'll get lots of practice with this and like lab and discussion and stuff discussion this week again is going to be recursion。

😡，But yeah， I think that's like。I don't think I enough time to go through like fts that much。

 but we're gonna go over in discussion， so I can go over this then。

 but just a quick introduction to factactts。 facts are a visual representation of visual application of recursion。

 So're actually present any trailbox。 So like snowflakes， please things like that。

 But it's basically just a repeated pattern。 And and we do this in snap using command block。

 So you'll use like the move block and like the rotate block to kind of draw at these factorss at different levels。

 it's gonna take an input of a size and a level because factorss get infinitely more complicated as you increase the level。

 And this is something that usually appears on the in lab portion of the midterm。

 which more information will be coming on that soon。 So this is really important。

 but usually we don't cover it like that heavily in lecture。 It's more of like a lab thing。

 but I will be covering it in discussion on Friday。 So yeah。

 I think that is all we have time for today。 So you guys go。 I'll stick around if you have question。

 Thank you so much for coming。 I really appreciate it。 hopefully you learn something but。😊，Okay。Yeah。

嗯。嗯。嗯。Okay。Thank you落点落线。若分。

![](img/26ff02d7db4e57e2fd05eef0917bf429_13.png)