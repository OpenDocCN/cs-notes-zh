# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P22：22_06_03_计算简化模型.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/366a0d677a8702fce0796a75403b50e1_0.png)

We're going to begin by extending the abstract machines that we talked about in the last lecture。

 the very simple machines to try to get to a point where we can have a model that help us understand computation in the most basic possible way。

So here's a starting point really the way Turing thought about it。

 so our goal is to develop a model of computation that encompasses everything we know about computation。

 every process that we use to compute things， and we want to make that model as simple as possible。

So think about the mechanical process of adding two numbers。

 so this is a very familiar computational process， we take the two numbers and compute the sum and then perhaps there's a carry in this case the carry zero now we compute those and we get a two and we have to carry the one。

Now we add the three ones and we get a three。And then that's get a carry of a 0。

 And then the3 and 7 gives a 10， which we have a carry of one。And eventually bring down that one。

 and we have the result， the addition of the two numbers。Now it's a simple process。

 let's think about its basic characteristics。It's discrete。 We do one thing at a time。

 maybe we have a small part of amount of memory to carry the few digits that we're adding together in the carry and so forth。

It's local， we move from one place to another that's pretty nearby。

 we're not jumping to a place a mile away ever in this process。And it's got states。

 we're always doing something， it's kind of well defined that we're in a certain state with a certain amount of data。

 and then that's going to tell us what to do next。Those are the basic characteristics that Tring wanted to have in his machine。

Now in the previous lecture， we talked about discrete deterministic finite automata。

 and that's an abstract machine that solves a pattern matching problem。So just to review。

 there's a string on an input tape， no input no limit on its length。

The machine reads each character once， moving left to right。

 lights up yes if it recognizes a string and no otherwise， and each DFA defines a set of strings。

 that's all the strings that it recognizeds， that's the purpose of the machine。

And we did an example of a machine that to show how they're built。

 they have a finite number of states， each one's labeled YN， we have transitions between the states。

 each labeled with a symbol。One of the states is identified as a start state， we begin there。

 read a symbol， that symbol tells us which state to move to next。

 we move to the indicated state and we repeat until the last input's been read， turn on yes or no。

 and we did a simulation of this particular machine which recognizes all strings whose number of bes is a multiple of three。

In this case， it winds up in the yes state and lights up the yes light。

So that's a very simple machine that has all the characteristics that we thought about in the example where we're just adding numbers。

And we saw at the end of the last lecture that there are some things that we can't do this with this machine that we'd like to do。

So what we're going to talk about now is the equivalent to the model that Turing came up with called a Tring machine。

It's like the DFA， but it's got a few more things that it can do。

 It's an abstract model of computation。 Again。 we have a string specified on a tape。

 No limit on the length of the string。The Tring machine now can read。

 but it can also write characters on the tape， and it can move left or right。

 It's not constrained to just move in one direction。And again。

 it's going to light yes if it recognizes a string and no otherwise。

 but it also might halt and leave some result of the computation on the tape。

So here are the differences with the FAAs it can write。It can move left or right。

 and it might halt and leave a result on the tape。A very simple abstract machine with just those extra capabilities over what we saw with DFAs。

 that's a Tring machine。Now Tring defined his machines mathematically in terms of tuples that define the states and relationships among tus。

 but this graphical model is just as formal and accurate a description。

So we're going to look at the details of a couple of touring machines。

 they're quite similar to the DFAs， so again we have a finite number of states， each labeled Y or N。

 but also HLRR for halt move left move right， and we have transitions between the states the same as before。

 but now on each transition there's a pair of symbols。

One of them is the input symbol and then the transition tells what state to go to if you see that input symbol。

 then there's a call in and then an output symbol which saysr that indicated output over the one that you read。

And the other thing is， if the state that you're going into is labeled L， then move left。

 otherwise move right， and keep going until you get to a state labeled yes or no or halt and turn on the associated light。

So lets at， we'll look at an example in a second， but let's talk again about the similarities and differences between DFAs and Tring machines。

They're symbol models of computation， they have input on the tape that's a finite string。

 but there's no limit on the size of the tape， finite number of states。

 the state transitions are determined by the current state and the input symbol。

The differences are with a DFA， you can read and put symbols from the tape with a Turing machine。

 you can read or write， read from the tape or write onto the tape。DFA。

 you can only move to the right。 and every time you read a symbol。

 you move to the right with a Tring machine， you can move in either direction。

DF is the tape itself it's finite， it's a string and the Tring machine there's no limit on where you can go in the tape in either direction。

And the FAAs， we go one step per input symbol。 if you have end characters on your string。

 then you can only do end state transitions with the Tring machine。

 there's no limit on the number of state transitions that you can do。 That's a big difference。

And again， DFs， all you can do is turn on yes or no， but with the Tring machine。

 you can also leave output on the tape which gives a great deal of more power to that machine。

But the basics are very， very similar， so let's look at an example。So this is a touring machine。

 a three state touring machine that can decrement a number given on the tape。So in our notation。

 the sharp sign is just an empty symbol on the tape， and we can assume that wherever we go。

 there's going to be a sharp sign on the left or right。

And then our input in this is going to be a binary number on the tape。

And we start in the state labeled R at the left， the arrow from nowhere coming in indicates that's the starting point。

And we're starting with the tape head on the leftmost symbol that's not blank， in this case， the one。

So。What this machine does is going to move to the right as we come into the start state。

One thing to note just to keep the notation down is that if we see zero and write zero and stay in the same state we don't bother drawing those so in this case there's an implicit I saw a zero I saw a one I write a1 and I stay in the same state so omitting those makes the machines much simpler there's lots less state transitions so if you see a symbol write that same symbol and stay in the same state we don't put that that transition there。

So if you're on a symbol and you're in a state and you don't see an arrow with that symbol。

 you can assume that you stay in that same state and don't write over the symbol。

 So now we're still in that state and we see a zero I's going to write a zero and move right。

So really， what this particular state means is scan to the right until you find a blank。

And so that's what we'll do。In every case， see it， we write it and go back into the state when you go back into the state。

 you move right。So now in this case， now we see a blank and then we write a blank。

 but we move to the middle state。And that states an L。 So we move left。

So now what we do is we're in that state in the middle， it says if you see a zero。

 write a1 and stay in the same state， so we write a1 and then going back to the same state。

 move left。And so what this one is doing is writing ones as long as you see a zero。

Now at this point we see a 1 at that point， we write a zero and then go to the halt state。

So our input was 101010000， and our output is what's left on the tape is if that's a binary positive binary integer。

 what we've done is computed the result of subtracting one from that integer。

 that's a binary decrementer。So just one point about this， what happens if we try to decrement zero？

So if we happen to have the number zero on our tape。呃。That's fine。 We find the blank。

 But now we're going to go left looking for a one。And we're not going to find one that this Turing machine doesn't halt。

 it'll keep scanning over the blanks， looking for a one and remember the tape's infinite in either direction。

 so it'll never halt。So this is a bug， Tring machine can have bugs just like a Java program。

 so in order to fix that bug in this case， think about what we need to do。

What we need to do is at least if we see a blank go transition to the halt state。

And then maybe decrementing zero， we have an overflow if you want to do something different you could as well。

 the main thing this fix does is avoid the infinite loop。Okay。

 so that's an example of a complete Tring machine that does a useful computation。Here's another one。

 This one is supposed to increment a binary number。So now the input is 10。

100111 when we increment that we do kind of the opposite computation。

 we want to change all the ones to zeros and then the rightmost0201。

So here's the Turing machine that gets that done again。

 we scan to the right until we find a blank and at that point we know we're at the right most endpoint of the number。

See the blank， so we go into the state at the middle， state at the middle， if we see a1， we write a0。

And we keep doing that as long as we see onces。Until we see the first zero。

 the right most zero in the input， and if we see that， we write a1 in halt。

And that's then the output when we haul， and so we take that input to that output。

 which is adding one to that binary number。So already。

 we're doing familiar computational tasks with this quite， quite simple machine。

And with a little bit more work we can develop machines to do more complicated tasks just by the way this one actually does keep incrementing。

 making the number bigger if you have all ones， it'll make them all zeros and then it'll change the blank just to the left of the number to one。

 so itll actually grow the number by the length of the number by one。

 and so this will just keep counting and incrementing without stopping increment any number。

So now we can put these two together actually to make an adder， a machine that can add two numbers。

 that was kind of one of our original goals。So what we're going to do is here's the plan to compute x plus y。

Now remember when we're looking at this that we're not going to talk about efficiency today。

 we're just talking about whether we can do it or not Next lecture we'll talk more about efficiency。

Right now， we're just interested in is this machine powerful enough to do the computations we want to do。

 So there's some way to do it， and then we can worry about doing it faster and better later on。

So here's how we're going to compute x plus y we're going to go so we can say we have two binary numbers with a plus sign in between。

 that's our problem and what we want to do is replace that problem by the sum in binary。

So the plan is move right until we find a blank and that'll put us at the right end of y。

And then we'll decrement why every time we decrement y will'll。

Find the go left to the left of the plus sign。 it will be right at the right end of x。

 We just decremented Y， and now we're going to increment x。

And then we'll just continue doing that until we decremented y equals0 so that means we started with y。

 we decremented by1 down until we got to0 and that's when we can tell that if we come to the plus sign when we're looking for a way to stop our decrementing the case that we did when we're trying to decrement  zero and then in that case we know we got to y equals 0 every time we decremented y we incrementmented x so that's going to give the same result as adding y to x and so then we just clean up by erasing the plus in all those leftover ones and what we're left with is the sum of x and y on the tape。

So that's a strategy for computing x plus y， and it's an example of a Turing machine that can add two numbers。

Again， quite， quite simple， formal abstract machine。

 but it can start to do a more complicated tasks and you can start to see and say well。

 if you can do that then you can maybe multiply in the same way and so forth and sure enough you can。

So anyway here's what the binary adder looks like， it's a combination of our decrement machine and our increment machine。

 and then in the middle one that cleans up so we start at the bottom left and then find the right end and then move up to decrement Y。

So after having done that then we go and we increment X。

 you can follow through the details of this offline。

 I just want to show the basic plan so then increment X and then just now we keep going and doing the same thing。

 decrement Y and increment X until we get to the point where we tried to decrement zero and we got all ones and ended at the plus。

 so then we go into the middle to clean up and eventually come to the halt having computed the sum of x and Y。

So with just six states in combining the two machines that we've talked about。

 we have a Tring machine that can add to binary numbers。Not too bad。

 that's the basic computation that we want to be able to perform and we're able to perform it。

So that's an introduction to what a Tring machine is Now what we're going to want to do is the same thing that we did with a DFA we're going to want to write Java programs that can simulate Tring machines。

They're quite simple abstract devices， and we should be able to do that。

The main task that we have to accomplish is this idea of simulating an infinite tape。

So that's what the machine has， the DFA didn't have that， it just had a finite tape。

So what we're going to do is use two stacks to simulate a tape that's infinite on both ends。

We know what the stack abstraction is， so now we can write Java programs that take care of that and it's taking advantage of the idea that we don't when we build a stack。

 we don't have any limit on the size of the stack and that same idea is going to give us infinity in each direction。

So here's what it looks like。 So we're going to have a left stack and a right stack。

 So that's everything to the left of the tape head and everything to the right of the tape head。

 And we're going to assume that the current character being read is at the top of the right stack。

So you can see those two stacks， which the one on the left is everything to the left of the tape head。

 but we don't keep the infinite blanks， we just keep one blank representing infinite number of blanks to the left or to the right。

And as we keep pushing， then we are adding to the size of the stack。

 but we still always carry implicitly the idea of unlimited amount of tape。

So what do we do to read a character well if the right stack is empty。

 that means there's nothing to the under the tape head except a blank we assume that it's a blank so we return a blank if the right stack is empty。

 otherwise we pop the element from the right stack。

 that's what we're going to return as what was under the tape head。

And then now the next thing that we do is is going to be right in whatever character that we're going to write in our Tring machine。

 we always read and then write every time that we read a character we write some other character so we're going to call right exactly once after each call on read and that's implicit in this implementation。

 so then whatever character gets is supposed to be written gets put back on the right stack in the tape head then will be on top of the right stack and it'll contain that new character that was just written。

So what about moving to the right， that's the other things that we have to be able to do with our tape。

 we have to be able to move the tape head to the right or move it to the left。Well， again。

 if it's empty。Then moving to the right is putting a blank on the top of the left stack。

 otherwise what we put on there is what we get from popping the thing on the right stack the most of the time move to the right means just pop the right stack and push it on the left stack。

 then the next character on the right stack is the one the tape head is under。If it's empty。

 then we have to put a blank and moving to the left is the opposite。If the left stack's empty。

 we push a blank otherwise， we pop from the left and push that on the right。 So with two stacks。

 we have a very simple implementation of the basic operations that we have to perform for a Turing machine。

Given the basic facility that we just talked about using pushdown stacks to simulate the operation of a two way infinite tape。

 then it's easy to write Java code to simulate the operation of a Tring machine。

 just extending what we did for DFAs。So again， we have an instance variable。

 which is our current state and a start state。And then we have an array of characters。

 which tells us for each state what action we're supposed to perform if we wind up in that state。

Then we have an array of symbol tables which tells us for each state。

 which state we should go to for each possible character。

 and then we have another array of symbol tables which tells us for each state what character we're supposed to write out for each given input character。

 so for example， if we're in state1 and we see a1， then we should write out as zero as indicated in the diagram and is indicated by the center element in the center row in the rightmost array。

So those things provide all the information that we need to go ahead and simulate the operation of a touring machine。

So our constructor is just going to fill in the data structures and then to ass simulate the operation of the Tring machine。

 we go ahead and start in our start state， and then we take our input from standard input and just push it all on the stack and then now our right stack has our input and then we can simply move through the machine as indicated by the state transitions and the rugs。

 as long as their action is not the halt， then we read a character。

 and then that character depending on what state we're in。

 we go to the symbol table associated with that state and we get the character that we're supposed to write。

And then we go to the other symbol table and we get the integer associated with that character。

 which tells us what state to go to next， and then depending on whether that state is an R or an L。

 we might move right or move left and that's the whole thing we just keep going until we find a halt。

And if we do get out of there， we return the to action according to the associated with the state that we're in。

Then our main is going to be similar to the main and DFA。

 which just reads a string from standard input and runs the machine on that so in here we're using TM as abbreviation for Tring machine in a couple of different places so。

If we read， this is the。Turing machine for our decrementor， so if we give it the string 0，0，0111。

 then it decrements it and anything that we might want to put， we can decrement。

So very simple Java program that we can use to simulate the operation of any Tring machine。

 all we have to do is then if we get all zeros and we get all ones and so forth。

All we have to do is provide a。Full representation of everything about the machine。

We need the number of states， we need the alphabet。

 the number of different characters that the specific different characters that might be on the tape。

 and we need the start state。And then for every state， we need its type or its action。

 the transitions that for every character tells us what state to go to next。

 and then the output characters which tells us for every character what character to write。

 that's a complete description of the Tring machine。

 and given that this Java program can simulate the operation of that machine on any input。

That's what we use to study the behavior of Tring machines is this program and all the examples we give are the result of running this program。

But it turns out that the ability to do this is actually quite profound。

 and that's what we're going to look at next。

![](img/366a0d677a8702fce0796a75403b50e1_2.png)

![](img/366a0d677a8702fce0796a75403b50e1_3.png)