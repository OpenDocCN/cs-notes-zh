# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P23：23_06_04_通用性.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/5b16a7fbea9884097815c4862fbf5f36_0.png)

Turring's contribution was not just developing such a simple model of computation。

 but also showing that it was powerful to do any powerful enough to do any computation that we might imagine。

That concept is called universality。That a turing machine is nothing more。

And then a finite sequence of symbols。We have our decrementary turing machine that we drew out graphically。

 but we had a text file representation of it that's just a bunch of symbols。

 so in particular what we can do is we can put a Tring machine and its input on a Tring machine tape。

Just lay out this table with spaces in between with different symbols on the tape。

So there's an input we might want to run on the left and then this complete description of the Tring machine。

 Tring machine and its input all described with a finite sequence of symbols。

 and what that means is that we can then develop another Tring machine that can take that as input and simulate its operation。

Since any Turing machine can be described with finite set symbols in this way。

 this Tring machine that uses this as input is going to be able to simulate the operation of any other Turing machine。

 just like our Java program did。That's the idea of a universal Turing machine。

 a Turing machine that takes as input， any other any Turing machine。

 an input for that Turing machine on a tape。So that's a particular machine called a universal Turing machine。

 and that's our example where we had our increment input to our decrementator Turing machine and then our decrementative Turing machine。

 you could put any Turing machine there。And then what the universal Tring machine does is leave on the tape。

 precisely what the Tring machine that's on the tape would leave on the tape。

 if it were run on that input， or if that machine loops。

 the universal Tring machine would loop or ends and yes no。

 it would do exactly what the Tring machine that's on the tape would do。In this case。

 it would wind up decrementing the number input by one and blanking out the rest of the tape。

Turing figured this out that simply simulating a Turing machine is a simple computational task。

 you can do it with the basic operations that we have laid out for a Turing machine。

 so since it's a simple computational task there's a Turing machine to do it。

 that's a universal Turing machine。Maybe an easier way to think about it is look at everything that our Java simulator does and each piece of it think about building a turing machine。

 a piece of a turing machine that could do that。Really often all we're doing is going and looking up in a table what state should I go to next and so forth。

 It's quite a simple computational task our simulator gives a roadmap for it we don't have to build a constructor because everything's already on the tape but simulating the infinite tape we don't have to worry about that part of it because the Turing machine already has an infinite tape most of it is updating the state as I indicated。

So if you want to see the details or build your own Turing machine for any computational task。

 this is something that there's lots of resources for。

 in fact we have a whole Turing machine development environment on the book site and one of the things that's there is a 24 state universal touring machine that you can go ahead and study and run on our decrement or or any other Turing machine that you want simulates the operation of any Turing machine if you put the input in that Turing machine on the tape。

If you think the 24 is a small number， actually people have developed universal Turing machines that have only four states with six different symbols。

Just warning， if you get into working with Tring machines and you like working with discrete processes and programming。

 it can be addictive and you'll find lots of examples on the book site of Tring machines that people have developed for all sorts of computational tasks。

But the idea of universality is really profound。 a universal Turing machine is a very simple model of computation that's universal actually in a precise technical sense。

 we're going to call a task computable， if a Turing machine exists that can compute it。

And what Turing proved is that it's possible to invent a single machine that can be used to do any computable task。

 so that's the proof is the existence of a universal touring machine。That's Tring's main theorem。

 one of his main theorems。And so one thing is that if you can simulate a Turing machine。

 you could actually simulate a universal Turing machine， so if any machine that you make。

 if it can simulate the operation of a Tring machine。

 then it can simulate it can do any computable task because in particular it can do a universal Turing machine。

 which can do any computable task。And that means that in terms of what you can compute。

 any one machine is universal， we don't have to build separate computers for each tasks that we might encounter like solving scientific problems or doing email or playing music。

 it means that all the computers， all that we can invent our equivalent。

 they're universal in that they can do anything that a Tring machine can do。

 which means they can do any computable task， and that's a very profound result that has lots of practical implications as well。

Here's just an example。 maybe you've seen this example's called the Game of Life。It's a different。

Simple formal model of computation called a cellular automaton。

So we think of an infinite square grid with cells that can live and die under specific rules。

 It's discrete。 time proceeds in discrete steps。And。

There's a couple of rules that determine whether cells live or die。

So it depends on the values of its eight neighbors。 If a cell has two few neighbors alive。

 either zero or one， it dies of loneliness。If the number of living neighbors is just right two or three。

 then it's going to live to the next generation， and if there's too many alive。

 more than three it dies of overcrowding。And then the other rule is that a cell is born if it has exactly three living neighbors。

 These are simple rules。 And you see how they work in just a second。

 So suppose we have this configuration at a particular time T。

Then what we can do is for every cell you can count the number of neighbors。

 it's eight direct neighbors， and these are the counts for this and you can figure out what's going to happen to each cell based on those counts。

 the one at the fringes are zero， there's a couple that have exactly three。

 and there's one that a couple that die of loneliness and one that dies of overcrowding and you can check that in time T plus1。

 we get a different configuration。So the question is。

 what's the story with this discrete model of computation really is a model of computation。

 as you'll see。So the idea of Conway's game of life is that even very simple rules like that。

 even simpler than Turing machine can lead to pretty complicated behavior。And very early on。

 one of the things that people realize is there's a thing called a glider and after one， two， three。

 four steps， the thing has the same form， but it moves moves down through the grid。

 and again it's infinite in all directions so if you get that configuration， it'll move。

Now you can write a Java program to implement the game of life to see what happens。

 and I wrote one that's how we get the demos， some of the demos that we've done here。

 it's a very simple program that maybe could have been an assignment when we discussed arrays。

But the input to that program can lead to interesting and complicated behavior。

One thing that's quite amazing is a thing called a glider gun if you start out like this。

 then here's what happens。It lookss pretty complicated， but after a while， what you can realize is。

That。This glider gun， it bounces around at the top there， but it spins off gliders。

And when you think about it， that's actually pretty profound that we can get that kind of behavior from such simple rules。

Those gliders out there， that's transmitting information。And if we can transmit information。

 maybe there's more that we can do， and there's another level。

 there's a glider gun breeder that generates glider guns that all generate gliders。

 extremely complex behavior。So one thing that someone has figured out is what happens if you have that starting configuration。

 pretty complicated starting configuration， but if you study it just for a minute and you can well you have to study it quite a bit。

 but you can understand when I say that actually what that thing is is a universal touring machine。

 you can kind of see the tape going off along the diagonal and then the state diagram as a little array down in the bottom left。

So with the game of life， we can build a universal Turing machine。

 and that means anything that we can compute， and that's the Tring machine's definition of what we can compute。

 we can compute with the game of life。 It's quite surprising。

 It's a very profound connection to the real world。And what church and Turing articulated。

 and this was because many people who were working on different models of computation and they were trying to see if one would be more powerful than another。

 like we saw with our one stack and two stack machines at the end of the last lecture。

 by the way a two stack machine， as you saw when we simulated a tape with two stacks。

 you can make that like a Turing machine。So tooth stack machines are equivalent to turing machines。

 so therefore they can compute anything tuuring machines can in their equivalent。

And what church and Turing articulated is that anything that we can do in this universe is going to be equivalent。

 that a universal Tring machine， it can simulate an universal Tring machine。

 universal Turing machine can simulate it so they're all equivalent all compute the same thing。Now。

 this is something that can't be proved because it relates to the universe。

 physical properties of the universe， it could be falsified， but we can never prove that it's true。

So the thing is ever since this thesis was articulated if someone wants to study a new model of computation or a new discrete physical process。

 we can use simulation to prove that it's equivalent to some known physical process or model of computation that we already know to be equivalent to Turing machines。

 so we'll see later on in the course of a small machine that we define that we can simulate in Java and vice versa and when you have the Java compiler you can what that does is take a Java program and make it run on a simple machine so those machines are equivalent and with the Java simulator we show equivalentence one way with Turing machines and when you can show equivalentence the other way with a couple of steps。

In general， it's not difficult to use simulation to prove computational models equivalent。

And what that means is that if you believe that， then there's no need to look for a machine that can compute more once you've got past the two state machine。

 it's all about convenience and efficiency but not about the kinds of problems that can be solved and that is very important because it enables us to have a rigorous study of what computation is in this universe if we believe the churchturing thesis。

And there's a lot of evidence in favor of this because many， many。

 many models of computation have been shown to be equivalent， and this is just a short list。

 some of which came from mathematicians trying to come up with more powerful models of computation and others that just arise practically as people develop different ways to compute things。

In fact， over eight decades， people have developed lots and lots of different models of computation and still going。

 and they all turn out to be equivalent in terms of the problems that can be solved with the computational device。

 all starting with the Tring machine， this simple machine articulated by Tring as a definition of what we can compute。

these universal models sometimes bear a striking resemblance to nature。

 this is a model called a Lindamere system， which is a formal model not much more complicated than toring machine but then can be linked to graphical models that makes us think well is there computability actually to be found in nature。

 these kinds of questions are profound and important。



![](img/5b16a7fbea9884097815c4862fbf5f36_2.png)

![](img/5b16a7fbea9884097815c4862fbf5f36_3.png)