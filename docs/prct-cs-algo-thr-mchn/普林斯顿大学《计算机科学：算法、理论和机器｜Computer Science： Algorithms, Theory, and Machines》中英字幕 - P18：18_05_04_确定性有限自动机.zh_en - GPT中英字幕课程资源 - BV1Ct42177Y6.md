# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P18：18_05_04_确定性有限自动机.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/458b77fe1077c1dad01d1fb97cd03fe5_0.png)

Next， we're going to look at simple abstract machine called deterministic finite automaton。

 and remarkably this simple machine is going to help us with the problem of determining whether or not a given string is in the language described by a given regular expression。

So let's describe and define a deterministic finite automaton。

It's an abstract machine that actually is built for the purpose of solving a pattern matching problem；

 that is there's a string specified on an input tape， no limit on the length of that input tape。

 string can be any length， whatever。And what the DFA can do is to read a character on the input tape exactly once moving from left to right。

You gets to read the character and then move on to the next character。

After it's read the whole string， it's going to light up the yes light if it recognizes this string。

 the no light otherwise， so it has internally programmed the idea of what set of strings it's going to recognize and it reads the whole string and then lights up the light depending on whether or not it recognizes it。

So with that， each DFA defines a language， it reads a string， it can read any string at all。

 and for some of them it lights up the yes light and those are the ones that are in the language it defines。

And for other ones， it lights up the nose light。 those are the ones that are not in the language that it defines。

 So complete correspondence between DFAs and languages are sets of strings。

So let's look at how to make a DFA and look in more detail， so here's an example of a DFA。

Where we talk about actually what's inside。So the first thing is it's got a finite number of states。

 so those are the circles in the diagram inside， and each one of the states is labeled Y for yes or and for no。

Also， there are arrows or transitions between the states。

 and each one of those transitions is labeled with a symbol。

The other thing is that one of the states is the start state。

 and that's the one in this case at the left with an arrow from nowhere pointing to it。

So the way the rules that govern the operation of the DFA are listed as the bullet points。

We begin in the start state。Read one of the and put the next input symbol and move to the state that it indicates from our start state。

So every state has a transition leaving it labeled with each character。

 so whichever character it happens to be， that says which state to go to next。

 and we just keep going until we've read all the input。

And then we're going to be in one of the states after that process， and if we're in a yes。

 we light the yes light and if we're in an N we light the no light。

 so let's look at an example for how this DFA operates for this string。

Is this string in the language defined by this DFA or not。

So we're in the start state and we' read a B， so it says that what we should do is read that B and go to the middle state。

Now we're in that state and we read a B， and again， we go to the right。Now in that state。

 we see an A in the state at the right， we see an A。

 and the transition says just read that A and stay in that state。And again。

 read that A and stay in that state。 Now we have a B。

 So we go back over to the first state on the left。Read a B， go to the middle state， read an A。

 stay there。Read a B， go to the state on the right， and read a B， go back to the start state。

Now we've read all the characters and we're in a state labeled Y， so we light the yeslight。

So we say that that DFA recognizes that string， or the string is in the language defined by the DFA。

 the set of strings defined by the DFA。Here's another example， another string， same DFA， read the B。

 go to the right， read an A， stay there， read another A， stay there， read a B， go back to the left。

Read a B， go to the middle， read an A， stay there， read a B。

 Now we've read all the characters and we're in a state labeled N， so we light the no light。

That string is not in the language defined by this DFA。Very simple set of rules in every DFA。

 as long as it has states with transition for every character that it might read for every state can follow these rules and eventually either light up yes or no。

DFA operates according to very simple rules， one thing that we can do to better understand it is to write a Java program that simulates the operation of any DFA。

This is what we do to get our examples and quiz questions and so forth。

So what's that going to look like well， the instance variables， well there has to be the start state。

 and then we have a Boolean array that says whether it's a yes or a no or does it recognize the string or not？

And then we have an array of symbol tables for each state， we have to know for each character。

 what state we go to next。For example， for state one， the one in the middle。

 we want to if we get an A we want to go to state1， if we get a B， we want to go to state2。

 so we have a little symbol table mapping A to1 and B to2。

 so represent those tables that represent the data structures that we need in order to represent the state in the DFA。

And then so our constructor takes a file and we have a file format that basically has the same information and the constructor will just read that in。

 so maybe this is our file format which is the number of states， the alphabet。

 the letters that we have to worry about seeing on the input， the start state。

 and then the values needed for these tables and so any of us can write a program to read that file and to fill in those data structures。

So what's interesting is the routine recognizes， which takes the string on standard input and simulates the operation of the DFA returning true if it recognizes the string and false if it doesn't。

So we start at the start state and then。Sorry， we take the string as a parameter to this as an argument to this method。

 and then we want to print out whether or not it's in the language recognized by the DFA。

So for every character in the string all we do is get that character。

 so that's input that care at I and then we get the state that in the symbol table so next of state is a symbol table do get gets the entry corresponding to that character and that's a state and we just reset the state to that and then when we're done we've read all the characters then we just return true or false depending on which state we're in and so our。

Our test client can make a new DFA from a file name given as an argument and then it can read through standard input and can read a string and then print out yes if the DFA recognize it and no if it doesn't so for example。

 we can run it and say well as BA B BA in there and it says yes， what about BB， it says no。

 and we can type in any string we want and have a simulation of the result of running that DFA to recognize that string。

Pty interesting idea that we can with really a one liner simulate the operation of this abstract machine。

 it's an abstraction but we can write a program to try to understand what it does。

 and that turns out to be a key concept in theoretical computer science that will come back to again and again。

So here's just again， like the pop quizzes on regular expressions。

 you have the same kind of thing on DFAs and these get to be pretty complicated we actually really need these programs to check these kinds of questions。

 they make good quiz questions and you'll certainly encounter them if you have any kind of quiz in this kind of material。

So which of the following strings as this GFA is out toed that it set the set of bit strings that end in one。

Well， no， because it accepts 0110， say and that one doesn't end in one。

 and there's lots of strings that it don't end in one that accepts， but to answer the question。

 we just have to find one。It's kind of easier to say no than yes for this kind of question。

Equal number occurrences of 0，1 and10。 Well， no， theres plenty again， there's plenty of examples。

Bit strings with more ones than zeros。 Now， you could do lots of zeros in the first state and then a one with lots more zeros than ones。

Equal number of occurrences of0 and one， no these strings that we just gave。

 this one that we just gave disproves that。Bit strings with at least  one，1。 Yep， that's the one。

 And there you have to reason that it accepts all those bit strings and only those bit strings。

 That's why these types of questions are challenging to answer often。

Here's another example so what following sets of strings is this one except？Well。

 does it accept the set of bit strings with at least one one？

Well no in this case here's a bit string that's got11 but it doesn't accept it。

 it first transition stays in the no state， then the one takes it over to the yes。

 but then two zeros it winds up in the no state， so it's in that language but this one doesn't accept it。

Equal number of occurrences of0，1 and 10 again， same argument。

 this string will wind up in the no state， so it's in the set， but it doesn't accept it。

More ones than zeros， well no， that's not it either and you can reason yourself why that one's not it。

Equal number of occurrences of 0 and1， no， that's usually a tough one when you've got a loop because you can just spin in the loop as long as you want。

Actually， this one's a kind of complicated way to recognize a pretty simple language。

 just the bit strings that end in one， the only thing you can say about a bit string in this language is in the language recognized by this DFA is that it ends in one。

Again， studying these types of questions and looking for others in the book or in the book site is a worthwhile activity to better understand DFAs。

Now why don we talk about DFAs in the context of regular expressions， Well。

 there's a very important reason a theorem going back 50 years or more now。

 more than 50 years called Cly' theorem and it's an observation based on the idea that we've just seen two different ways to define languages。

 we've seen regular expressions， you give a regular expression it defines a set of strings。

 and we've seen DFAs that also define a set of strings。呃。So for example。

 the set of all strings made up the characters A and B with the number of occurrences of bes and multiple of three。

 that's the DFA， the one that we've looked at， and that's the regular expression。

 two different ways to define sets of strings。Remarkable fact is that these two ways of specifying sets of strings are equivalent。

So that is， given any regular expression， theres a DFA that accepts the same set of strings。

And given any DFA， there's an R regulargular expression that matches that same set of strings。

 so they're equivalent equivalently powerful Now there's sets of strings that you can't specify with either one and we'll talk about that later on。

 but the idea that these two models of specifying languages are equivalent is really profound idea and for now the consequence of this is there's a way to solve the regular expression pattern matching problem。

What we can do is in Cly's theorem， gave a constructive way to build the。

Deterministic finite time time corresponding to the given REE。

 that's how we proved or exists in automaton as he gave a way to build it and then use our program to simulate the operation of the DFE。

DFA， so that's a fine way to solve the Re powder matching problem from Cly's theorem。

 And that's what we're going to examine next。

![](img/458b77fe1077c1dad01d1fb97cd03fe5_2.png)

![](img/458b77fe1077c1dad01d1fb97cd03fe5_3.png)