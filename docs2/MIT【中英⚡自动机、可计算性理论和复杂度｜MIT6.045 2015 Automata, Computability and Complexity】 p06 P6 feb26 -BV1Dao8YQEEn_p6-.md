# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p06 P6 feb26 -BV1Dao8YQEEn_p6-

Okay， so I guess we'll get started， so you those of you who are here on time will get a special treat that you'll get to learn what universality is all right。

So so on Tuesday we okay， so just the administrative stuff PSet2 is out now。

 so you know I apologize that you've got you only have a week and a half to do it。

 but we're you know。We have a little catching up to though all right so it shouldn't be too bad so it's due Friday of next week and the other thing Tuesday of next week Robin will be lecturing again okay so last time we talked about touring machines about about what are they。

 the church touring thesis that you know is this sort of informal statement that you know touring machines actually capture what we want to capture by saying something is computable okay we defined the set of computable languages。

 which are just all those languages for which there is some touring machine that decides them。

And you know we gave an example of a touring machine for computing for recognizing whether your string is a palindrome and on PSE2 you'll do one more example of a touring machine that's and that one we're not even asking you to write out the whole state diagram just to describe the machine show that it exists so I mentioned last time that with enough effort you can rig together a touring machine that will add two numbers written in binary or that will sort a list of numbers or in fact that does anything you can do with any programming language that you can think of。

 and the fact that all of the different programming languages that and computing paradigms that people have come up with over the last。

8 know that every one of them can be simulated using a touring machine。

 you know this is sort of the empirical basis for the church touring thesis this is sort of why you people came to accept it as reasonable okay but now there's one particular thing that a touring machine can do which is maybe the most important of all the things and this is something that touring already noted in his you in his original paper of 1936 and this was not the main point of the paper know this was like an observation along the way the main point of the paper was to solve the Hilbert Un Shiings problem that I mentioned on Tuesday showing that there is no general decision procedure to decide the truth or falsehood of any mathematical statement and we'll see you。

We'll see that later in this lecture okay but along the way touring you know made an observation which is sort of the know entire basis for the software industry right you I call it the existence of the software industry Lema okay you know。

 which is that you know。Well， it's the following。So let's just state it as a theorem。呃。

Says that there exists a particular touring machine。Call it you。Okay。

 now I need to make a little bit of a digression， before I can finish stating this theorem。😊。

So here's the thing， right， what is a touring machine， right。You know， you have some initial state。

 you have this， and then you have a bunch of transitions to other states。

 like if you're reading a zero， then read a zero， you know， sorry right。

 then keep it a zero and move to the left and transition to this state， if you're reading a one here。

Then， then。Make it a zero and go right and stay in this state and so forth。Okay。

 that's what a touring machine looks like okay， but you know I've clearly only you know sort of I could specify everything that's important about this picture using a finite amount of information right I could so you know as a first step I could make it a table。

What happens in state1 and what happens in state2？Be call， we'll call these states one and two。Well。

 that depends on whether we're reading a zero or a one， right？

So if we're reading as zero in state one， then we。Do this if we're reading it so this particular touring machine clearly never halts。

 okay it just does stuff forever， that's fine if we're reading a zero in state two then sorry so zero go to the left and transition to state two。

Okay if we're reading a zero in state two， then we write a1。

 we go to the left and we transition to state one okay if we are reading a one in state one then what do we do we read a zero we go to the right and we stay in state one if we're reading a one in state two then we write a zero。

 we go to the right and we also transition to state one okay。

So any touring machine can be specified by a table like that one okay but now once I have that table。

 you know I could clearly write it out as a sequence of bits right all the information in this table you know I could do so well you know okay this L and R these are just bits right that's just a zero or1 these numbers here you know that tell you which state to get the numbers here to tell you which state to go to you know these would have to be written out in binary maybe you know I would need special delimiter symbols to tell me when the zero or1 starts or stops okay but you know I could do this I could say zero and maybe L means zero and then two is。

1 L。 So I've just specified this row， right， and then。This one would be 1001 right，1 for this。

0 for the L and then01 to represent the 1， okay and then this one would be 0，1 for the R and then 01。

 and this one would also be 00101。Okay so so there's a string of 16 bits you know that would represent what this touring machine does okay and if something was halt and accept and maybe I'll write that as11 and if it's halt and reject I'll write that as00 or something you so you know it doesn't actually matter the exact encoding scheme that I use right all that's important here is that you know there is some we can clearly come up with some consistent scheme for taking that table and encoding it as a string of bits okay so now let's let M be this touring machine。

 okay and then the description of M as a string of bits。

 I'll write like this I'll write with M with angle brackets around it。

And now the interesting point is that this description of a touring machine could itself be written as an input on a touring machine tape right why the hell not okay so you know which is saying we can have programs that take you know other programs as input we can have touring machines whose input is the description of another touring machine okay。

 and then what can we do with that well all right now I can state the theorem okay so what touring showed is that there exists a particular touring machine call it you such that。

呃。For all touring machines， M。And for all inputs， X。You know， strings of zeros and ones you。

Of description of M comma x equals M of x。 Okay， so what's this equation saying anyone？Yeah。Exactly。

 yeah， this is saying that you is an interpreter for him， right yeah。

Oh all right excellent question so yeah， so I have a you know I wrote this as a touring machine that takes two inputs。

 okay， but we saw on Tuesday that you know that that can easily be arranged right one way to arrange it is indeed。

😊，You know， be like the simplest way in practice， so to speak， is to just have。

Description of M written on one tape and to have the input X written on another tape， right then。

You just reads both of these tapes okay， you know， in fact， you know， if we're going to prove it。

 then you know the theorem and this is by far the easiest way to do it， okay， however。

 because of the equivalentvalence of one tape and two tape touring machines。

 you know because all these things can all kind of simulate each other， you know。

 that's the church touring thesis。😊，It would also work perfectly fine just to have M and X written on the same tape。

Okay， just you know， in different parts of it， okay， you know。

 this is you know something that we know well today right。

 you you know when you're you know using your laptop， okay you know。

 the executable files are in the same you know memory you know。

 as the data that they're operating on， okay， they can live in the same memory。

 they can live in different memory， you know， it's all fine。Okay，You know， so programs can be data。

 okay， that's， you know， this is essentially the fundamental concept of you know the stored program computer。

 okay。How do we prove this theorem well the proof you know is not all that interesting is simply to construct the touring machine you that does this thing okay and so this is basically just a programming exercise right it's you know writing a an interpreter for the touring machine language and writing it in touring machine okay so how would it work well。

So basically， what you want is for， you know you is going to be reading its M tape and it's going to be that going back and forth on the M tapepe in order to figure out how to act on the X tape the way that M would act。

Okay，😊，So for every one step that M would take， just on its own。啊啊。

actcting on the input X U is going to do a much larger number of steps okay because you you know's let's say they you know they've got the same input on the X tape they're in the same position but now U has a lot of work to do just on the M tape in order to figure out what it is that M would do if it's in you know you the appropriate if M we're in the same situation know and part of the problem here is that U has to be a single fixed machine right the size of U cannot grow you know as a function of M U is fixed for all time but M could be arbitrarily large M could be much much larger than U itself is okay so U you know does not have enough room to store in its own internal memory you know what is M state right。

You just cannot remember that you know， use only hope is to store you know the information on this tape about you know you know that that will help it remember what is M state okay。

 so so basically what we can do is we can。We can divide up the M tape into different you know regions。

 say one region for each state that M could be in okay and within each region say the state 1 region right part of it will just be this description over here you know this description that tells you what are you supposed to do if you're okay so let's say that that the description of the state starts out with a label for the state like this is the state labeled 01 and then we need a description of what you're supposed to do if you're in state one like you're supposed to do the action that's encoded by 0010 okay and oh sorry and also by。

嗯。1001。Okay。Okay， and。All right， this is a one dimensional tape， I should take that seriously。Okay。

 and then you know， we should also store a bit in order as just like a little pointer to remember whether we are in this state or we aren't in it。

 so let's say one if we're in it and a zero if or not。Okay。

 and then you know we also need some symbols all right I'll allow a nonbinary alphabet right。

 so I'll allow some hashes to say when I've started a state description and when I've stopped one okay and then after this hash I would have the description of the next state say the10 state where I announce its label I say what you do if you're in the 10 state and it's encoded by the string 01010101。

 you know and then I say that we're not currently in this state。😊，Okay， so then so now what we do is。

You know we have to you know just in order to simulate one step of M。

 we've got to first scan all across the Mta until we find this one that comes before a hash and it tells us which state are we currently in all right great now you know we learn something and then we've got to go back to the beginning and we've got to you know okay。

 so we move past this part and we see， you know maybe they're sorry there should be another hash or。

In between these got a hash prime or something after this guy okay and then we've got to check。

 you know first of all what is the appropriate know what are we reading on the X tape know are we reading a zero or a1 right and that's going to then determine what we do right so there's an instruction here for what happens if we're reading a zero there's another instruction for what happens if we're reading a1 okay so we move to the you know and we'll assume you know that these are the only two symbols that are allowed on the x tape so so that's this is really just a constant amount of information that you has to remember right I have to check what I'm doing if we're in you know reading a zero and what we're doing if we're reading a1 okay and then let's suppose that we're reading a zero okay then then I know you know where is the instruction for what I'm supposed to do next it's over here okay but now now？

I have to jump to the state that so this is telling me that I've got a。

Jump to state 01 It so happens that that's the same state that I'm already in okay but the machine doesn't know that right now right So now it's got to go scan all the way across the m tape again in order to find that state which is labeled by01 so you know and this will take some time because it can't remember that you can't even remember the whole label of the state。

 I can't even have all of that in memory at once okay but it's still okay because it can go and compare bit by bit know it can leave little crumbs along the way like it can say the first first。

 you know I'm going to you it's all simpler if I can add more alphabet symbols like you like0 with a check mark0 with an x mark you know it is fine you can introduce more alphabet symbols as long as you only have a constant。

of so I can sort of say， all right I know that I'm trying to jump to a state where the first bit of its label is a0 okay so now I go through all of these guys and wherever I see the beginning of a label of a touring machine I put a checkmark if it's a zero okay so I'm not gonna to put a check mark here okay but then now now know and let's say I put a checkmark over here to say that I've already read this bit now I go back and I read the next bit of the label I'm supposed to jump to okay and now I go and look for labels where there's already a checkmark on the first bit and I put one on the second bit and so forth so I've got to basically keep stling back and forth and back and forth until I find the label that's you know identical to the label that's written in memory that I have to jump to okay and then I know which state。

It to be next。You know it's， you know， by the way， I think this is simpler if instead of binary encoding。

 we use unary encoding， everyone that know what unary encoding is， so unary encoding just means。

I would encode zero like this， one like this。Two like this， three like this。It's a very。

 very inefficient encoding scheme， but it does make touring machine programming simpler。

All right so all right， so you so the details of how all this works are you know ultimately not that interesting right it's basically just well it's how it's how you write an assembly language interpreter in assembly language except more painful than that okay you know inuring actually gave an explicit machine you in his paper and it turned out that there were mistakes in it so then he had to publish inerroum you know in 1937 but you know whatever。

 doesn't even matter， okay you know he didn't have good debugging tools available because you know actual digital computers didn't exist yet。

 so you know。😊，Okay， but the important point here is that it is enough。

 you know if we thought of it this as an engineering problem。

 you know it is then enough to build a single machine U and from that point forward。

 you know we can just get you to emulate any other machine M just by encoding the description of M onto U' tape and M can even can crucially M can even be much more complicated than U itself is okay so we can have a machine that can simulate machines that are much more complicated than itself。

That's the interesting point here。Okay， so this is all。

Very very impressive so then at some point you know the question becomes what can a touring machine not do right okay so so we'll discuss the famous example of what a touring machine can't do which which is the halting problem so so we mentioned on Tuesday that you a touring machine can inherently you get into an infinite loops know it does have commands to stop but if it never hits one of those commands then it's simply going to run forever so and know and this is true for reallife programs also that they can get into infinite loops and so you know you might wonder wouldn't it be great if we could have an infinite loop checker right and when you first like think about this like if you've just been。

to programming a little bit like this doesn't actually sound like that much to ask for right because you you stare usually if you stare at a program right it's pretty you it's not that hard to tell if it has an infinite loop or it doesn't if it says for I equals one to n well that's not an infinite loop。

 but if it says do I equals I plus one go you loop then well that is an infinite loop at least until I exceeds the the maximum integer suck which we're not worrying about here because we're assuming that we have unlimited memory available。

So it doesn't seem that hard and in fact there are debugging tools that you can use that will very。

 very often in practice be able to tell you whether your program has an infinite loop or it doesn't okay you know first of all there are many programs where you just prove that they do something and that they halt and they do that thing and there are many other cases where you know your debugging tool can just easily tell you that your program has an infinite loop okay but you know to see like just intuitively why the halting problem should be difficult why you might expect it to be difficult you know to tell if a computer program is going to stop running or not you know it helps to consider some different examples okay so let's。

Just to be clear on what we're talking about。So we'll define halt to be the language。

That consists of。All descriptions of touring machines。Such that。M。

 when run on a blank input halts Okay， so I'll just write like M parentheses to say M is run on the empty string as input。

Okay， you know， we could also， we could have a variant of the halting problem where。

We were interested in all。Pairs， but a touring machine， M and an input X。

 such that M halts on input X， that's also fine。呃。And I'll sometimes talk about these two interchangeably okay either one。

 I'll be happy to call the halting problem right as we'll see they're basically equivalent anyway okay but let's for now just define this to be the halt thing problem okay you know so I give you a I described to you a touring machine and I ask you when this touring machine is run on a blank input。

 is it ever going to stop。That's what I want to know。U。So。So to see why that might be a hard problem。

 let me show you an example， of a very simple computer program。I think this is this is， I don't know。

🤢，This is， this is， this is basic or something。 Or this is， this is an infinite version of basic。

 Okay， but it could be pascal。 It could be， you know， Java。 It could be whatever you want。 Alright。

 so， so I'm saying， I'm， I'm going to loop。 You know， let me make this end。

I'm going to loop over all even positive integers and four and greater okay and you know I'm never going to stop so you know you know if I'm programming and touring machine。

 I'm allowed to say something like for end to infinity。

 right which just means keep incrementing and forever and ever。

 using more and more memory you know as needed。Okay。呃。Good。

 now I'm going to loop over all p's from1 to n minus-1。嗯。嗯。All right， fine， offset calendar here。

I'll set S to be zero here。Good， there's my program。Okay。That's the whole thing and okay。

 so our prime is not， you know， you know， if we really wrote out the program in full detail。

 we could check whether they're prim by just looping through all possible divisors and seeing whether any of them divide it。

 that would just mean adding one more loop to the program right？Okay。

 so this is a program now can anyone sort of describe to me in words what this program is doing？Well。

 it's like under what condition is it ever going to halt？

It's going to halt if there is an end with what property？Yeah。こするさん。Yes。

 it's going to halt actually if there's an even number which cannot be written as a sum of two primes。

 okay， even number for or higher that cannot be so written okay now people have actually checked all the even numbers up to I think10 to the 17th or something you know something ridiculous and every single one of them you know four larger that anyone is checked is a sum of two primes okay。

 there is a famous one of the most famous conjectures in math from the 1700s says that every even number for higher is a sum of two primes anyone know what that's called。

Gold box conjecture okay so this program here is simply halting if and only if gold box conjecture is false okay so which means that if you had a general program to solve the halting problem or in other words to check you know whether infinite loops exist you know infallibly then you could just immediately solve gold box conjecture because you would just feed it that program and you would ask whether it halts right you know a huge you know a huge number of the other great open problems of math could be immediately solved in the same way the Riman hypothesis you know all sorts of other things of number theory by the way not not not every mathematical question can be can be you know do we know how to phrase in this form in terms of whether some particular touring machine will halt okay but a huge number of them we do know how to phrase that way okay so。

So so this is this should already give you you know some indication that the halting problem might be kind of a hard problem。

 but this is not a proof right you know and in fact in some sense this is very much what David Hilbert in 1900 was hoping for you know he was hoping for you know a general mechanical procedure you know that would just after a finite amount of time just tell you the truth or falsehood of gold box conjecture or the Riman hypothesis or you know any other math problem right that anyone could could ask okay so you know and who's to say that it's impossible okay well you know I guess tourings to say it's impossible okay so。

So to give you the general proof of the unsolvability of the halt thing problem right I mean you I think it's one of the highlights of human thought right you know it's the selfreential argument you know I'm sure that some of you have seen it before。

 but you know if you've never seen it before， you know then you it's my privilege to show it to。

You know because this is no ordinary theorem， I thought that you know I'd first introduce it with a poem there's a very famous a poetic proof of the unsolvability of the halting problem and then we sort of turn the poem into prose okay but you know' it's a very very easy proof by the way。

 you know you know sort of you know you do incredibly little work you know for the result that you get out you know and this has sort of been a gold standard for us ever since you know to get to get this much by doing this little work okay so so the poem that's by the linguist Jeffrey Po it's called scooping the Lo snooper okay an elementary proof of the undecidability of the halting problem okay no program can say what another will do。

 now I won't just assert that I'll prove it to you I'll prove that although you might work till you drop。

 you can't predict whether a program will stop。Imagine we have a procedure called P that will snoop in the source code of programs to see there aren't infinite loops that go round and around。

 and if P prints the word fine no looping is found you feed in your code and the input it needs and then P takes them both and it studies and reads and computes whether things will all end as they should as opposed to going loopy the way that they could well the truth is that P cannot possibly be。

 because if you wrote it and gave it to me， I could use it to set up a logical bind that would shatter your reason and scramble your mind。

Here's the trick I would use and it's simple to do。

 I'll define a procedure will name the thing Q that would take any program and call P， of course。

 to tele it loop by reading the source， and if so Q would simply print loop and then stop。

 but if no Q would go right back up to the top and start off again。

 looping endlessly back till the universe dies and is frozen and black。

And this program called Q wouldn't stay on the shelf。 I would run it and fiendishly feed it itself。

What behavior results when I do this with Q when it reads its own source code。

 just what will it do if P warns of loops， Q will print loop and quit。

 yet P is supposed to speak truly of it， so if P' is going to quit， then P should say fine。

 which will make Q go back to its very first line， no matter what P would have done Q will scoop it。

 Q uses P's output to make P look stupid。If P gets things right， then it lies in its tooth。

 And if it speaks falsely， It's telling the truth。 I've created a paradox Ne as can be And simply by using your putative P。

 When you assume P， you stepped into a snare。 Your assumptions have LED you right into my lair。

 So how to escape from this logical mess。 I don't have to tell you。

 I'm sure you can guess by Redductio or cannot possibly be a procedure that acts like the mythical P。

 You can never discover mechanical means for predicting the acts of computing machines。

 It's something that cannot be done。 So we users must find our own bugs。 Our computers are losers。

That's the pill。So all right， so let's just unravel that into prose。呃。So。So like many proofs。

 this is a proof by contradiction。 Okay， we do is we suppose by contradiction that we had a program。

P， we had a you know， a touring machine， we might as well say P， which solved the halt thing problem。

 Okay， what would that mean Well， it would mean。The P would take his input a description of an arbitrary touring machine M。

And P would halt and reject。If MHtz。And P would halt and reject。If M runs forever。

 we agree that this is what it would mean to solve the halting problem。Okay。

 well now using this program P， the key step is that we're going to use it to create a new touring machine queue。

 that does something a little bit different， but very closely related。Okay。So。

So we claim that ifP exists， then certainly there also exists a touring machine queue。

That does the following， it takes as input， a description of a touring machine M。

 and then what it does is it runs M on M's own code as input and it does the opposite of whatever M does。

So in other words， Q on Emma's input is going to loop。If。M， given a description of M Htz。And。

Q of M is going to halt。If M， given the description of M， runs forever。Okay。

 so now can anyone just sketch for me， you know， given P， how do we create Q？So I mean， you know。

 forget about touring machines， you know， just imagine that you're programming in an ordinary programming language。

 okay， and imagine you know you've got a subroutine that does you know that solves the halting problem for you。

 okay you've got a subroutine that does P now by calling that subroutine。

 you know how are you going to do Q？Yeah。Yeah， well okay。

 so so I guess there are two issues that we have to take care of here right the first issue is that you know P was only a machine for solving the halting problem for machines that take the empty string is input right。

 but that's not actually that big of an issue okay why not。

 because I claim that you know if I know a touring machine。M， let's say and an input X。

 then I can surely create a touring machine， say M prime that does on a blank input。

 what M does on input X。Okay， so in other words。Right， if I know M and I know X。

 then I can make a touring machine that will do this。 Okay， how do I do that anyone？

How do I get rid of the X， in other words？Yeah。To first draw。Yep。

Exactly all I do you know and this is again something that you know from programming experience。

 you can just take your data and hardwire it into your code if you really want to right just you know instead of reading your data from a file just it put it at the beginning of your program right so in this case we could say you we have M prime just first write X on the tape which you it had hardwired onto the it had like a collection of states whose only purpose is to just go and output X on the tape and then go back to the beginning and then the rest of it will just simulate what M would do。

Right， very simple so okay so Q can certainly call P on that you know m prime as a subroutine where here you know the only difference is that you know x happens to equal description of M itself okay for reasons that we'll see later okay so we call P to ask whether you know M given its own code as input will halt or run forever and then if the answer is that it will halt then Q just enters an infinite loop just you know。

😊，Like do I equals I plus one loop， you know， just an infinite meaningless loop okay and and if Pete says that M on input M runs forever then Q halts doesn't matter if it accepts or rejects。

 okay， it just halts okay， now can anyone you know do the finishing move here。

 how are we going to get a contradiction？I've set this up for you。Now。

 what can we do with Q that will reveal an absurdity？Yeah。Yes， we feed Q， the description of Q。Okay。

 and we ask what happens then？All well， you know there's two possibilities right。

 it could halt or it could not halt okay but you know if we just trace this through。

 well if Q halts on its own description then you know then that is saying that well Q was supposed to run forever on its own description right if Q runs forever on its own description。

 then that was telling us that Q is supposed to halt on its own description。It's a contradiction。

So the only possible conclusion， I mean， the only assumption that we made in this whole thing was that P existed。

 so the only conclusion that we can draw is that P cannot have existed。😊，Okay。So。Yeah。Okay。

 so there's one particular way of sort of making very， very vivid。

 you know the nature of the halting problem that I really like a lot， okay。So I'd like to show you。

And this is also appropriate for MIT okay， these are called the busy beaver numbers， okay。

 and so these were invented in the 1960s as a sort of a way to make the halting problem very very concrete okay。

 and what they are。Okay， so BB of n is defined to be the maximum number of steps that any touring machine with n states。

 let's say over you know。With with one tape one two way infinite tape and the alphabet 01 you know these are just details okay can take you know on an initially blank tape meaning a tape that's just initially filled with zeros before halting okay so of course the maximum number of steps that a touring machine can take you is infinity you could always just have a touring machine that goes into an infinite loop okay but now you know we're avoiding that problem by saying just among all of the touring machines with n states that do eventually halt if you start them out on a blank input which one runs for the longest number of steps and that is what we call busy beaver of n the touring machine is supposed to be this beaver going you know which is very busy obviously because it's going to run for quite a long time。

あ。嗯。Okay， so the thing that I've defined here is just a sequence of positive integers。

 right that's all it is， so we can try you know， just like with any other sequence of integers。

 we can try to work out the first few values。Okay。诶。

So can anyone tell me what is busy Beaaver of one， what's the largest number of steps that a one state touring machine can take on a blank tape。

 which is not an infinite number of steps？Yeah。Just one， well why？There mis saying。

Exactly your first step had better say to halt because if it doesn't then you know because you only have one state you're just going to be doing the same thing forever right oh I mean you could sorry you know you can say if you're reading a zero then change it to a1 and if you're reading a one then halt okay fine so you can get you know a little bit but but we're going to count that as being only one step because the halting itself we're not going to count as a step so so we're going to say that busy beaver of one equals one。

Okay， busy beaver if two。This one is more of an exercise to work out。

 I think in past years I've put it on a PSet to work it out， but you know it's not that enlightening。

 I mean you try a bunch of things and eventually you find that this is equal to six okay you can make it to state。

 you it's a very fun problem if you'd like to amuse yourself you can you know if someone wants to know do it and post it on piazza that could be cool okay but you know you make a machine that。

You know， with two states and it runs for six steps and then it halt。Okay， all right。

 so busy Beaer three。So what's the most number of things that any three state touring machine could do All right。

 well that you know， you know now there starts to really be a large number of possibilities right there are a lot of you know like tens of thousands I think of different three state touring machines so this actually took a research paper right to work out this value you know but in the 60s or 70s people did it and they found that the answer was 21。

Great， all right。😊，Busy Beaaver of four Well， this was another research paper。 you know。

 I think by the 80s people had worked this one out and this one was turns out to be 107。 All right。

 you know， this doesn't look that bad， right？Busy Beaaver of5， turns out that no one knows the value。

Okay， so so you know so basically you know you know what you have to do is you know you have to look at all possible five state touring machines and you know and you know all the ones that halt you know give you lower bounds on busy Beaaver of5 right but then among the ones that don't halt if you want to say that you've determine the value the hard part is that you know all these ones that seem to be just running forever。

 you got to prove that they run forever because of any of them eventually halted well then that would dramatically increase the value of busy Beaer5 okay say this is actually a problem people are working on。

 I actually I' worked once with a student at MIT who was trying to pin down busy Beaaver5 you know they got it down to think there's about there's only about 25 state touring machines right now that are still in question where you where no one can prove whether they halt or don't halt you know because of you might say the unsolvability of the whole。

But while we have as a lower bound on it， we know that it's at least 47 million176，870。😊，Okay。

 it's probablybable， you know， you know， and maybe it just is that。

 but to show that it is that you have to show that these 20 machines that are still in question will actually run forever and then not all。

Okay。And I think that eventually we might be able to prove the value of busy Ber5。Busy beaver of six。

 it seems quite likely that we'll never know the value。Okay。

 what's known is that it is at least  three times 10 to the。1730 power。It may be much。

 much larger than that。😊，All right， so what's going on here？Okay。So。

So one can prove a theorem about how fast the busy beaver sequence grows。

 which basically says that it grows faster than any sequence you have ever seen in your life unless you've seen something like the busy beaver sequence so if you've seen the super fast growing functions like stacked exponential functions or the ackerman function if any of you have seen that anything like busy beaver just blows all of those out of the water it grows faster than any sequence of numbers that you could define using any computer program to be a little more careful we call a sequence of numbers computable if there is a program that takes n as input and that outputs the end element of the sequence so on Tuesday someone ask me the question after class。

 why do we only consider touring machines that accept or reject？

Not touring machines that could do output something more complicated and the answer to that is we do consider touring machines that can output things that are more complicated okay except and reject as just know a very。

 very simple behavior that's often very convenient for theoretical purposes but if you want to consider a touring machine whose output is a whole integer you know say that's written on its tape you can absolutely do that as well and you know in fact touring's paper was called uncomputable numbers so you know yes。

 you can have a touring machine that computes numbers right and so you so it's easy to define you know so a computable sequence you know is one where there is a touring machine。

Let's say whose output on on input n is the n element of the sequence。 Okayy， an example the。

Examples of computable sequences， the squaring function。That's a good example。

 the exponential function， okay， not hard to see that that's computable as well right you can easily design a touring machine that will take n as input and that will output two to the end Okay。

 you know， you could have。Two to the two to the two to the two， you know， to the n times。 Okay。

 that's computable。 By the way， you know， this has a name。 This is called tation。Okay， you know。

 there's another thing which is called penation， okay， what'sation， well like a sorry。

 a penated to the B is ateated to itself B times。😊，Okay。

 where you know where ateated to the B means a to the A power B times。😊，Okay。

And you can have sexated， Okay， you can have， you know， I guess heptated。 you know。

 you can keep going like this。 Okay， And then what's the ackerman sequence， by the way。

 a simple way to define the one way of。Defining the Ackerman sequence is the first。

Element is one plus one， the next element is two times two， the next you know。

 four okay for those you know watching from home， the next one is three to the three 27。

 the next one is fourterated to the four， which is four to the four to the four to the four。

 which is you know。Already rather large， the next one is five penated to the five。

 which is fiveteetated to the five。Try it to the five and so forth like that。 Okay and so on。

 That's the Ackerman sequence。 Okay this again is a computable sequence right you know you know it's you know I could give you a homework I won't but I could give you a homework problem to just write a recursive computer program that computes ackerman of N you know you'll only be able to run that program up to three or or maybe four you know and then nothing you know anything larger than that it'll just run out of memory Okay but you can write the program right so this is a computable sequence So this theorem is telling you that you know the busy Beaaver sequence grows way。

 way， way faster than that。😊，Okay okay， so how can we prove this theorem， I'll give you a hint。

 I've already given you a key tool for doing it。😊，Can anyone guess how we might prove that the busy beaver sequence grows faster than any computable sequence？

Well' as usual， let's argue by contradiction， yeah，Yeah。Exactly， everyone hear that。😊。

Proof is supposed by contradiction that we have a touring machine that computes these busy beaver numbers。

Suppose M is a touring machine that computes the ends busy beaver number then I claimed that we could use M to solve the halting problem。

 which we already showed was impossible Okay how do we do it Well， basically you know。

 think of all these。Like here are all the possible end state touring machines and now just imagine that I'm plotting how long each of them runs when I start them on a blank tape right some of them run forever of course they just go off the board some of them halt almost immediately you know a few of them like run for a really long time and then halt and the halting problem you know is I'm given a particular end state touring machine and I want to know whether it halts and know I can of course one thing you can always do solving the halting problem is you can just simulate your machine for a long time you can just keep running it and running it if it ever halts well then you know the answer you know you know it halted okay the problem arises if it you've run for a really long time and it still hasn't halted then what right then you know you know you can try running it for longer but you know if it never halts。

 you may be at this for an infinite amount of time so but now let's suppose。

that you knew busy Beaer of N。Or in fact， let's even suppose that you knew anything that was an upper bound on B Be for a event。

so in fact， all I need is this， right？I just have the output of some touring machine。

 which I know is some upper bound on busy Beaaver of N then now I can actually make this approach work because all I have to do is take my touring machine call it P and I have to run it for up to M of n steps and see if it's halted by then if it has then it halts。

 but if it hasn't then at that point I know that it never will halt because M of N is an upper bound on how long any touring machine with the requisite number of states could ever take before it halts so the ability just to guess you to write a program that just guesses any upper bound on the busy beaver function would give us the ability to solve the halting problem from which we conclude that there can be no touring machine that computes any upper bound on the busy Beaaver function。

Okay。So you know， there's。There's more you can say about it。

 you know I'll probably have a little bit more about this function on the third piece that， I guess。

哎。So you might say that the busy beaver function is already sort of scraping up against infinity right in some sense。

 all right， so but we might as well just go for it and just talk about infinity。

So so so so so here's a question right， you know， you might wonder like is the halting problem just a rare anomaly like you know。

 like yeah， most of the problems that you want to solve are computable but there's a few weird ones that are uncomputable right you know。

 now if you're like you know in like，Practical situations that may be a pretty good heuristic right like most of the problems that we tend to talk about you know in real life。

 you they're very often computable problems like you know multiply expentiating， sorting searching。

 stuff like that if they weren't computable usually we wouldn't even be talking about them unless we're mathematicians or something but there's another sense in which actually it's the computable problems that are the rare exception almost all problems are actually uncomputable this is actually a very。

 very close analog of the fact that we proved way back in the first lecture that are second lecture that you know almost all booleying functions require exponential size circuits it's only a very。

 very rare some very， very rare outliers that have small circuits you know even though the argument didn't give us a single example of a function that。

circuitsIt showed us that almost all of them did in much the same way。

 I can give you an indirect argument that shows that almost every in some sense。

 almost every language is uncomputable， although that this argument doesn't give us any example of such a language。

Okay。So this will actually just you know， the proof of this really just amounts to the proof of you know。

 one of the greatest theorems in the history of mathematics。

 okay and this is the theorem of Cantor from the。😊，From the 1880s。

 which says that there are different kinds of infinity。

 okay there are not all infinite sets or you have the same cardinality， some are larger than others。

So。so。You knowSo there's an obvious sort of philosophical question here。

 which is how do you even measure the size of an infinite set right。

 you know if you know what sense does it even make to say that one infinite set is bigger than another Okay。

 so you know， there's the。You know there's the standard paradox which Galileo already puzzled over you know in the 1600s。

 okay of you know， are there more numbers than there you know are there more integers than there are even integers right it seems like in one sense。

 yeah， obviously there's twice as many okay but in another sense。

You know there's exactly one integer for every even integer right the two can be placed in one to one correspondence with each other like this right and so you know so like I'm sure many of you have heard the story of Hilbert's hotel where it's a you know hotel with an infinite number of rooms you and it's fully occupied but then you know an infinite number of new guests arrive and you but they can still all be you know very easily accommodated because you know just move all of the old guests to you know move that move whatever guest was in room end the room to in you know great now you've got infinitely many vacancies so you know so so there is something strange about the sizes of infinite sets okay but you know the definition that Cantor adopted was just to say two infinite sets have the same size if and only if their're elements can be placed into one to one correspondence with each other okay so you know if there's a mapping you know like this one that maps every element。

The one to element to a unique element of the other， then we'll say that the sets have the same size。

 so in particular there are just as many integers as there are even integers okay。And in general。

 we can call any set countable or countably infinite if its elements can be placed in one to one correspondence with the integers。

 okay， that's what countable means。Or accountably infinite。Okay。And。

And countable in some sense is the lowest level of infinity okay it' the smallest infinity and it's also denoted using the Hebrew letter Ol okay Ol it's called Ol Ze okay Canther was also a mystic you know he thought that you know in like discovering these different levels of infinity he was showing like that God was even more transcendently great than had been known。

 he actually you know he tried to get the Catholic Church interested in this。

 you know they sort of they were not very interested they rebuffed him this you know and then he spent the last like 20 years of his life in an asylum okay this is all true okay but one of the you know。

There's a book called Logic Comics that tells the story of Canther and also Bertrand Russell and Gerdo。

 it's a graphic novel， it's co-authored by a friend of mine， Christto's P Dimitri。

 I very strongly recommend it， but if you'd like to know some of the history here。

But you know so it turns out that countable infinity you know already captures quite a lot。

 you know more than one might have expected， so you know one of Canther's first observations was that the rational numbers are countable okay。

And anyoneone know why？Well， yeah。I see I see people making a motion with their hand that basically just amounts to a approve。

 Yeah， so yeah， so what you can do。😊，Is you can make a gigantic table that has every rational number in it somewhere。

So let's just suppose for now that we're talking about the positive rationals， okay？

Then we can make a table like this。Okay， and by the way。

 you know this table will not represent every rational number uniquely right， for example。

 this one is the same number as this one okay but that's fine。

 we just want to make sure that we're hitting every rational number at least once okay and then if we want to place these in one to one correspondence with the positive integers。

 all we got to do is say well this is the first one， this is the second one。

 this is the third fourth。Fifth。Sth， seventh， you know， and so on。

 and we just sort of zigzag through， you know， diagonally， right？

Just capturing more and more of them as we go outward。Okay， in the same way。

And more relevant to our purposes， I claim that there's only accountable infinity of touring machines。

 why is that？Anyone。Yeah。So we could。Ppresents each one。Yep。Exactly yeah。

 exactly every touring machine can be you know uniquely coded by a single positive integer namely just take the touring machines's you know table write it out as a finite string of bits and then interpret that string of bits as an integer I mean you know you have to be a little careful find if it has some trailing zeros so maybe you should always put a one at the end just to make sure that all these dentegers are unique okay but you know but every you know there's clearly only countable infinity of finite strings of bits right so lets let's list countable things。

😊，呃。Integers。Rations。Finite bestrs。Touring machines。Okay， the general rule is that you know。

 if it takes， like if you have a set and to specify a single element of that set， you know。

 it can be done with only a finite number of bits， then there's only countable infinity of things in that set。

 right because there can only be there are only countably many finite strings of bits right you know。

 because there's only countably many integers because that's what countable means， okay。All right。

 but then， as I said， Canther's great discovery was that this does not exhaust the kinds of infinity that we can have。

So an uncountable set is an infinite set which is so large that its members cannot be placed in one to one correspondence with the integers。

And now。The key claim here is that the set of languages is uncountable。Okay。So， how。

 so how do we prove that， All right， Well， so this is just， this is a version of， you know。

 Canther's diagonal proof， you know， which along， you know， with。Touring's proof。

 you know is another highlight of human thought Okay so again。

 I'm sure that some of you have seen it， but the idea is this， you know。

 let us suppose by contradiction that the languages were countable okay that so by by a language again。

 I mean just now an infinite set of binary strings。😊。

Okay or a finite one I just mean any set of binary strings okay。

 let us suppose that languages were countable okay。

 that would mean that we could put you know all languages in one to one correspondence with positive integers so there would be a first language。

 a second language a third and so forth okay， but what is a language。Well， language。

Has to specify for every possible bit string whether it is or isn't in the language okay so the empty string0100。

01，10，11，000 and so forth okay so I can just write a0 if a string is in the language sorry I could write a one if a string is in the language and a zero if it isn't so I could just start filling in this table right it's an infinite table that's you know but you know you got to start somewhere right so we could say all right。

 we've got the empty language how would I denote the empty language。啊。All zeros。

How about the language containing all strings？That's another good one。

How about the language of palindromes， It's a good one， so I want one。Anyone。one。One。1。Zero。0ero。1。

 one。Good， okay， how about the language of all strings whose hammingweight is even， tell you anyone？

1。one。Zero。one。0ero。0。One。Yeah。1。Okay， so you know。

 and then I could just have some totally arbitrary， crazy language， you know？

I don't know what this one is okay but it's there too because every language is in my list all right now you know。

 and it's an infinitely long list， okay， but now you know。

 then no matter how I made this list now can anyone tell me how I could get a new language which is not in the list？

😊，This is another thing that you can just prove by your appropriate hand gesture。Yeah。

 go down the diagonal， exactly。Okay， so all I have to do is go down the diagonal and flip everything that's there。

So。So I could define a new language by。1， zero， zero， zero， zero。

And so forth I've just flipped each of these guys okay now that language clearly will differ from every language on my list and at least one coordinate right。

 which means that cannot have been on my list， which means that contrary to assumption my list。

 you know despite being an infinite list that failed to capture all the languages， okay。

 which means that the set of languages is uncountably infinite okay， which means that in some sense。

 you know， you know if there are uncountably many languages。

 but there are only countably many touring machines okay and each touring machine you know it can obviously only compute at most one language。

 right there are some touring machines that just don't compute any language why not？😊。

Because they don't halt on every input， but among those a touring machine that halts on every input and accept or rejects。

 fine it computes some language， but certainly at most one。

 but if there's an uncountable infinity of languages。

 then in some sense almost all languages cannot be computed by any touring machine。Okay。

 so in some sense， if you pick a language at random by say flipping a coin infinity times， you know。

 to decide all infinity entries in this row， then the probability that your language would be computable would be 0%。

😊，It doesnn't mean that no languages are computable， just means that0% of them are。Okay， so。

 and there are many other examples of uncountable sets。😊，You know。

So a very famous example is the set of real numbers， okay。You know。

 basically because the decimal expansion of a real number or the binary expansion of a real number looks a lot like like this。

 looks a lot like a language right and you know in general we could also say，😊。

The set of all infinite binary strings。I is also uncountable。Okay。Infinite bit strings。Okay。

 so in fact， you know， all of these sets have the same cardinality。

 all of these guys can be placed in one to one correspondence with each other。

 so this is a second infinite cardinality。Which we call simply two to the o of zero。

This is like the exponential of all of zero。Okay， now by the way， you might be oh okay。

 so now you know， is a couple of questions you could ask one is well you know。

 is there anything bigger than this， is there anything bigger than two to the olive of zero。

 anyone know？So so so so so there is in fact， you know just like there's no largest integer。

 there's no larger infinity， there's no largest infinity okay we can you know no no matter what you know infinite set someone gives you you could always define a larger one just by saying the following so let's say S is your infinite set then you can consider two to the s which is the set of all possible subsets of s that's what it means and I claim that that will always be a larger set you know even if s is infinite okay you you want to see the proof of that like this is this this is canther is general theorem from the 1890s like you know it took them you know to get from this to this it took a decade this was hard to do the first time okay so。

How we do this Okay， so let's so I have an infinite set S and let's suppose by contradiction that there were a one to one correspondence between。

Between the elements of s and the subsets of s？So let's suppose by contradiction。

 that there were S had no more subsets than it had elements。

Then then that would mean that there would have to be a one to one mapping。

 call it F from all the elements of s to all the subsets of s。 Okay。

 so now I'm going to define a special subset of s， which I call T。And T。

Just consists of all of the elements of s you know that are not you know x that are not contained in F of x okay so I have this mapping right and you can see that this is kind of like the diagonal thing right I'm just saying I want to take all the elements of my set that are not contained in their corresponding subset。

Okay。And now I claim。Here the key claim is that t cannot be equal to f of anything。😡，Okay。

 so in other words， it cannot be in the image of F。 Why not， anyone？Well。

 because of the way t was defined， if t were equal， suppose t were equal to f of x for some x。

 then t would be equal to the set of everything in S that was not in T。喂。

Or sorry we could ask if x was contained in T， and it would be contained if and only if it wasn't contained。

Right。That would be a contradiction Okay so the conclusion of this is that if we look at like the set of all sets of languages。

 there are even more of those than there are languages。

 there's two to the two to the olive of zero of those okay no I should say。😊。

Let me just fill in this so sets of integers are also there's also two to the is of zero of those。

 those are also uncountably infinite， finite sets of integers you might want to verify are only countably infinite。

呃。OkayOne last question， does anyone know whether there's any set which is larger than all of zero。

 but smaller than two to the olive of zero， so in other words。

 is there an infinite set which is larger than the set of integers or smaller than the set of real numbers or larger than the set of touring machines but smaller than the set of languages。

 is there anything in between？Anyone。Well， that was I mentioned Hilbert's problems in the last lecture。

 his problems of the 20th century， this was his second problem right， is there anything in between。

 this was called the you know and the belief was that there was nothing in between。

 and this belief was called the continuum hypothesis。If you've heard of it， it's a cool name。Right。系。

One minute。So。The continuum hypothesis said that there are no infinite sets of intermediate size between the integers and the real numbers Canther spent decades trying to prove this and failed okay everyone else failed too the eventual resolution which was due to girdle and the Paul Cohen is it the answer to this question cannot be decided within the usual axioms of set theory okay you can stick in you know sets of intermediate infinite size if you want and they won't produce any contradiction you know in that you know assuming that set theory was consistent before but you could also not have them and that won't create any contradiction either okay so you know how could a mathematical question be undecidable well we'll talk about that next week when we talk about gird's incompleteness theorem this being one example of the phenomenon rearing its head but first you're going to learn about。

knowTouring Reducibility， stuff like that on Tuesday。

 how to show that other problems are uncomputable by reducing the halting problem to them。

 and the whole notion of reductions in oracles。Yeah。Good。どさは。

I've seen a lot of what piece that wine was due yesterday。I mean， I just decided this yesterday so。

Okay， I mean， I'm fine with also like。Oh， really。我表 meanで。 you know， that's what you have to do。Yeah。

 I'm right。yellow I'm sorry you。めとしう方がいい。Regardings question I guess。It will be to QM to do the M M。

That's right by M given a description of Amazon's input so let's say you had a program that you wrote and see who right you could say yeah that program read a file right。

 you could have it read a file which is its own source thing。

