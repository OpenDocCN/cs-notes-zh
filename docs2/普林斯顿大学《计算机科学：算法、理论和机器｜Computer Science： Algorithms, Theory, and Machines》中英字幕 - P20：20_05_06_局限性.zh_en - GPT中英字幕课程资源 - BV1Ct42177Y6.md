# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P20：20_05_06_局限性.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/aae8a81465995781878c1c96e2cc479f_0.png)

The concept I want to begin with in introducing theoretical computer science is the idea of limitations on the power of computing。

So let's see where we are so for programmers regular expressions are really a powerful pattern matching tool。

 we have a paradigm based on the theory that really facilitates the implementation and the combination of the two are very important in the real world。

For theoretians， there's the idea that we have two different ways to describe sets of strings and we know they're equivalent。

 but it's interesting to think about are there sets of strings there languages and machines that can describe sets of strings that we can't do with res and DFAs alluded to the fact that there are。

 but what are they， how do we address the idea of characterizing those types of languages and machines。

 certainly the DfaA as an extremely simple machines and we imagine there must be machines that are more powerful in the terms of having the ability to describe a broader class of sets of strings。

 but what are those machines like？For you， as we mentioned。

 you've got the core principles of computer science introduced to basic idea of abstract machines and languages。

 and we're going to use those things to get started on really addressing fundamental questions in theoretical computer science。

So here's the basic idea， so are there sets of strings that can't be described by any regular expression？

And the answer is yes， there are and we're going to do an actual mathematical proof that shows that you can't have an RE that describes the bit strings with equal numbers of zeros and ones。

 and that's just one examples there's many other examples。

 strings that represent legal regular expressions， there's no regular expression for describing those or prime numbers or another example from biology。

 complemented palindrome or palindromes， there's a long list of sets of strings that would like to work with that regular expressions are not powerful enough to describe。

And you might say the same thing about DFAs are there sets of strings that can't be described by any DFAs and of course by a Ky theorem that's the same question。

 you can't build a deterministic finite automaton to recognize say bit strings of equal numbers of zeros and ones and if you prove that then you've proved that you can't have a regular expression that specifies that language。

So that's a basic question and let's first be sure that we have a good answer to that first question。

 why is it that we say that deterministic， finiteatmata are not sufficiently powerful to do what we want。

 we have a limit on the power of these abstractions。

So our proposition is there exists a set of strings that can't be described by any REE or DFA。

And we're going to actually do a proof， we try not to do too many proofs in this course。

 but a couple of them are really important in this one you'll be able to understand。

So what we're going to do is prove this by showing that for this specific language。

 the set of bit strings with equal number of zeros and ones， no DFA can recognize that set。

So our proof is going to be by contradiction， so let's assume that we do have such a DFA。

It's a finite automaton， so that means the number of states is finite。

 so we can just say there's a number n， which is the number of states。So that's our first thing。

 let's assume that we can do that。So it's supposed to recognize strings the equal number zeros and1。

 so it's going to recognize the string that has n plus10s followed by m plus11。So for 1。

 so we give it 11 zeros and 11 ones， and it's going to go ahead and recognize that。

So we don't know what sequence of states that it goes through but it's going to go through some sequence of its states。

 it doesn't matter what it is as it reads each zero。

 it's going to whatever complex construction it is。

 it's going to go to some state and each time it's completely define what state it goes to next。

 whatever state it's in， follow the zero transition out。Now the critical thing is that since。

There's only in states。And we have n plus1 zeros。 some states going to get revisited。

There's not enough different possibilities to get through that without having some state getting revisited。

But that's crucial because what happens next only depends on being in that state。So。

What that means is if you take the zeros between the visits of that state。

 the machine can't tell the difference。It's going to whatever it does on that string with equal numbers of zeros and ones。

 it's going to do on this other string， it's going to start out 03，5 and once we're in position 5。

 it's going to do precisely the same thing for those two strings。

So there's a string of equal numbers of zeros and ones that it may recognize。

 but there's another one that has fewer zeros than ones that it's going to recognize too。

That string does not have equal number zeros and ones。

 and that's a proof by contradiction it's recognizing a string that we said it didn't recognize。

 so the assumption that we started with that such a DFA exists must be false。

That's a proof that there's a set of strings and pretty simple one that can't be described by any DFA or regular expression。

So that's a first result in theoretical computer science。

 there's a limit on what we can do with this kind of machine。So it's a natural question to ask is。

 so is there a more powerful machine like， for example。

 is there one that can recognize this language， equal numbers of zeros and ones。

 and the answer is yes， what we can do is add a stack to the finite deterministic finite automaton。

And I won't give the details， but I'll give a demo and you can understand how this machine works。

So with this machine， you get to， if you want， in a state。

 put the character that you just read on a stack。So let's look at how that one works in this example。

So we read a zero， we'd put it on the stack， read another zero， put it on the stack。

 when we read a1 and we have zero in the stack wed pop， but if the stack's empty。

 we put the oneands on。And now you can see that whichever character has appeared more is going to be on the stack and it essentially counts the imbalance between the zeros and the ones。

 and if the stack is empty and we get to the end， then it lights the yes。

So that's a more powerful machine that can recognize this other language it's interesting that just by adding a stack to a DFA。

 we can make it recognize machine of larger language there's also a formal language more complicated than regular expressions that defines the same set of strings there's a duality between machines and languages。

 but we're going to focus on machines just for now。

So what about more powerful than a one stack DFA yeah actually there's languages out there that if we add a second stack。

 we can recognize prime numbers， we can recognize strings that are legal Java programs， many。

 many other things and again， won't do the details of that just now that's really about the next lecture。

This is the way a theoretician thinks I've got the simplest machine I could possibly imagine。

 and if I add a stack I can do more than with the simplest one。

 if I add a second stack I can do even more and the question is where does it stop。

So we'll talk about this one next lecture， but the thing is。

 is there a machine that's got more power than a two stack DFA。

 we add a third stack and then recognize even more languages and the amazing answer is that no。

 not even a room full of supercomputers is more powerful in this sense than a two stack DFA。

That simple abstract machine from this standpoint is equivalent to a room full of supercomputers。

 it's a basic limitation on computation that we're going to talk about in the next lecture。



![](img/aae8a81465995781878c1c96e2cc479f_2.png)

![](img/aae8a81465995781878c1c96e2cc479f_3.png)