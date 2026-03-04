# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p03 P3 feb12 -BV1Dao8YQEEn_p3-

。Very。打败。あ。あかか。我。は。So I'm actually just going to stand by audio your visual is coming you should be here。

ま你外や。Okay，靠。都在没。These is are my key is an airring agency。All right。

 well why don't I just go over the administrative stuff while people file in？

So so the first thing is there's no class next Tuesday。

 right because Tuesday is on Monday's schedule because of President's Day。

 actually I only just realized that。実さ。Unfortunately。

 it means that we're sure to go off to a slow start and this course。

 you combine that with a snow cancellation but know that。That's okay。あこと。好了。

catch so although there's no class next Tuesday， I will have my regular office hours then anyway。

 if anyone wants to come， 11 to 12 next Thursday， unfortunately I won't be able to be here。

 but I'll have my postdoc， Robin Koorri giving a guest lecture， he's really excellent。

 he'll be telling you about context free languages， I think。

So it'll just be a normal lecture and let's see， so apparently the order for the Ser book and the student bookstore。

 can anyone tell me did they try to get it the book there and were they able to get it？嗯。

No one actually tried to get the book。Or you all just download it online or something Okay all right。

 fine。Okay， all right， well， if anyone actually wants a physical copy of the book。

 then it should be arriving to the bookstore so you can get it there。😊，Okay。

 so any questions about any administrative stuff before we get started？yeah。Yeah， I you know。

 so I just， you know， we wanted to make sure that everything would work out well but now it's set so that they're going to be posted at least very quickly。

Yeah， and they'll be accessible to you whether we end up using them more broadly that I have no idea。

 but you know， okay。So it's the first year that I'm doing this。

You knowI'm surging forward into the new technological world。Okay， so。Any other questions？All right。

So today we've got a lot to cover today， we're going to talk about the theory of a finite automata and regular languages。

 so we already sort of a defined finite automata a week ago and we gave an example of a finite automaton okay so remember you know a finite automain is just like a computer that scans its input in one direction。

 say from left to right， okay so it reads a bunch of symbols and as it reads them it maintains some state and it can transition to a new state you know depending on its current state and on the symbol that it's reading okay and then at the end it either you know accepts or rejects the string okay depending on what state it ends up in when it reaches the last symbol so that's basically what a finite automain is。

Okay a very， very simple kind of computer。 and to be a little bit more formal。

 And I just sort of invented my own variables last week。

 but I should probably try to stick to the variables that the Ser uses in his book。

 So so finite automain is specified by a set of states that it can be in know and this is always a finite set of states。

 know hence the name。 So we will call that Q。 there's also a finite alphabet。

 So that's just the set of possible symbols that the automain can read as as it moves along。

 you know a standard choice for an alphabet is just0 and one。 know， the binary alphabet。

 but you know it doesn't have to be that。 we could also consider larger alphabets。 Okay and then。

Fite automain also has a designated state called it start state Spser calls that Q sub0 okay it's the state that it's in before it's read any symbol and and then it has a designated a set of accepting states so so the automain accepts if and only if you know it ends up in one of these accepting states in this set F and then the thing that does the real work is the transition function Spser calls delta that's a function that just tells you given your current state and given what symbol you're reading what state do you go in into next know for reading the next symbol but you but that's all you know a little bit more formal than usually necessary usually we can reason about finite automata just by drawing pictures of them and just you know drawing arrows to represent the trans。

Okay， so we did an example of a finite automain last week。

 We did one that checks whether there are any ones in the string。 All right。

 so let's do one more example， just to， you know， refresh it in memory。 Let's do a。😊，So。

 so do you know what what， what the hamming weight of a string is。 So if I， if I write。

 if I have a sh。So so so just a little bit of notation okay first of all if I write like 01 star。

 that's just a set of all strings over the alphabet 0 and1 Okay it' the set of all strings of any length we'll see you know I think later in this lecture formally what this star operation is。

 but it just means take as many of these things as you want to okay including none of them if you want Okay so so 01 star is let me write it01 star is the set that consists contains the empty string you know that's fine the0 string。

 the one string 00，01。😊，10，11，00，0，001。Well， it goes on for quite a while all okay so a couple points to bear in mind here。

 so 01 star is the set of all finite binary strings， okay so01 star is an infinite set。

 you know it contains infinitely many strings but every string that's in the set is finite。😊，Okay。

 so so star means you know repeat as many times as you know take as many of these things as you want。

 but you know at any rate， a finite number of them okay we're not talking about infinitely long strings here okay so this is the set of all finite strings and of course you know the empty string which means the string of length zero you know is also a finite string so that also has to be included in the set。

By the way， know things to bear in mind， this is probably stuff that you would have seen in 6042。

 but。The empty string you know is not at all the same thing as the set containing the empty string or you know or the let's say you know if we viewed these as sets of strings。

 this is a set that has no strings in it okay but this is a set that does have a string in it。

 namely the empty string okay so you know it's like a Lewis Carroll type of thing yeah。Yeah， so yeah。

 okay， so oh so I write it like this， but you know what， I think Spster calls it epsilon。

 So let me thank you。 let me call it up let me write it as epsilon because thats that is what Sipster calls it Okay。

 you know， again， just you know， these are just matters of notation right。😊，So。But yeah， this。

 you know， being clear about this kind of thing， you know， something that can be useful and。

 you know， P sets， midterm stuff like that。 Okay， so good。 so okay。

 so so now if we have a string in 0，1 star。 So a finite binary string。

 then if I write like like this， the the hamming weight of the string is just the number of ones in it。

😊，Okay， that's what hemingweight means。And and now you know。

 one one thing we might be interested in is the set of all strings with a with a with a finite sorry sorry。

 the set of all strings， let's say with even hemingweight， okay， so let's。

Let's talk about a finite automain for that first just just a little bit more terminology， again。

 this is just purely the definitions。Okay， so so so first of all， if I have a set of strings。

 a set of finite strings。 So like a subset of 01 star， this I call language。

 and you know the terminology is kind of archaic because most of these you know the languages that we'll see in this course and we'll see a lot of languages。

 know， and they won't they'll be neither like you know English nor Chinese nor will they be like。

 say or pescal， they'll be like you know the set of all strings of even having weight or something like that。

 Okay but you know the terminology in this field is just any set of strings whatsoever can be a language。

 you know the original reason that people were studying this kind of thing had to do with human languages or programming languages。

 but you know it became more generalized kind of like you know in the history of math you know originally a function。

something like x squared or sine of x or something reasonable and only later did a function come to mean any possible mapping from this input set to that output set。

😊，Okay， so language is any set of strings over some alphabet here the alphabet is 01。

And we'll say that a machine， like let's say a finite automain recognizes or accepts the language。

 you know in this for now， at least they mean exactly the same thing， okay， you know。

 M recognizes the language and accepts the language if。

If M accepts all the strings over that alphabet that are in L and it rejects all the strings over that alphabet that are not in L。

 so it accepts exactly the strings that are in the language， okay。

 that's what it means for it to sort of recognize the language。Okay。So。

So now if we have a finite automaton M。That we can write L of M for whatever language is recognized by M okay and here we're using you know we're using the observation。

 if you like that every finite automain recognizes exactly one language right， namely just well。

 look at what it does， you know and take take whatever string。

 whatever set of strings that machine accepts， you know， which might be the empty set。

 which might be the set of all strings， you know which might be something in between。

 you know whatever set of strings M accepts， that that's L of M that's the language that it accepts。

Okay， and then our last definition。Is that we call a language regular if there is some so L is regular。

 if there's some M， you know such that L equals L of M， okay in other words， you know。

 a language is regular if it is recognized by some finite automaton。

 so the regular languages are just you know those languages that you know you can design a finite automaton to recognize them。

So all right， with that out of the way。I could now。Claim something。Like。

 let me consider the language。呃。That consists of， you know。

 let me make it odd havingway just to mix things up a little。The set of all x's。

 and here it's implied in 01 star。 so let's define L to be the set of all finite binary strings that have odd hemingway and now I claim。

That this language is regular， now to show that it's regular， you know。

 it would suffice to just come up with a finite automaton that recognizes this language。 Okay。

 so can anyone suggest to me how would we design a finite automaton that recognizes this language？

Yep。嗯哼。😊，やep。Yeah， all right， this one， I'm way ahead of I already picked that yep。Yeah。Excellent。

Yeah， all right， excellent that's exactly right So there we have it you know a two state find it automain for checking whether our string as an even or an odd number of ones right and you see how it works you know every time there's a zero。

 you stay in the same state every time there's a one you go to the opposite state okay and you know and by the way these two circles that that's a notation we use for an accepting state okay like we circle the circle if that state is accepting。

😊，Okay now。You'll remember that last week we also did an automaton that checks whether the string has any ones。

 and that one looked like this。All right， just a little change to this one。Okay。

And so that one recognizes a different language。Okay。Okay， so now here's a question。

 so let's let L be the language recognized by this automaton。

L prime be the language recognized by this one。 Okay， and now， you know。

 we could play games like I could say， well。😊，What if I'm really interested in the intersection of L and L prime。

 and I want to combine the two。 What does that mean。Well。It means is。呃。This is actually just。

 you know， I haven't done anything here。 Okay， because， you know， in this case， you know。

 one language is a subset of the other one。 You know， I'm just here。 I'll tell you what。

 Let's let's make it a little more interesting。诶。Yeah， how about yeah or I could do here。

 I'll make this one check for zeros。There we go。There we go， problem solved。嗯。All right。

 good so we've got L prime is the language of all strings that have a zero in them L is the language of all the strings that have odd havingming weight right you know these are two incomparable languages right there you know you know there are strings like。

111 that have odd havingming weight， but that have no zeros in them right there are strings like 000 that have no ones and sorry that have that do have zeros and that have even havingm weight and then there are strings like0。

01 that do have zeros and that have odd havingmingweight good。

So now let's consider you know L intersect L prime。

 which is the language of know all the strings that have at least10 and odd heming weight， okay。

 how could we design a finite automaton for this language， can anyone come up with one？

So this is a slightly more interesting example。Yeah。Mm。Yeah， all right， so excellent， so in fact。

 what's your name？Hung， okay， yeah。 So， so， so what what he was suggesting is actually something that solves a much more general problem than the specific one that we were talking about。

 Okay， so， so in fact。😊，Let's just go ahead and just abstract away from this particular L and L prime and just say something more general。

 okay？If you have any two languages that are regular， then their intersection is regular also。

 this I claim。Okay， so how can we see that？ Well， you know。

 a simple way to see it is via you know what we'll call the product construction。Okay where。

All you do is。So let's take our first automain， right， it looked like this。嗯。

One and here was our start state。 here was our end state， and let's just make two copies of it。

 put them side by side。 Okay I'm letting you know accepting be the up direction here。u。Okay， fine。

 Okay。 And now let's take the second automain and let's put that one in the left to right direction。

 Okay， so we've got what。1， zero，0，1。One。Sorry， zero。0，1， Okay， and now， you know， I'm。

 I'm interested in the intersection， which means， you know， okay， so my start state should be what。

 anyone。The star state of my new automaton。Like let's say the well， okay。

 I can make the choice arbitrarily， I guess， but let's say the bottom left one will be my start state。

 Okay， and let's say my my accept state will be what anyone。The top right。 Yeah， so。

 so what what am I doing here， I'm just basically。I've just basically defined the finite automaton that just simulates。

Having both of these finite an automata at once。 that's all it does right So it's like you know the state。

 you know， of each of these individually was one bit of information right and so with this four state automaton。

 it's keeping track of two bits of information， namely you know the state of each one individually right one of them in the left right and the other one and in the top down。

 Okay， and then I'm saying you know， I want to start in the state that corresponds to the start states of both of the automata and I want to accept if and only if we end up in the accept states of both of the automata。

if we end up in states that are except states for both of the automata so this is the sort of thing that we call a closure property。

 we'll see more examples of that right where we have some family of languages and then we verify that you know you can do something to the languages and you still stay in the family okay。

Good。So here's here。All right， here's the next question。Sorry。Yeah。Oh， oh， I'm sorry。Oh， right。 Okay。

 so let's。Good。Yeah， you're absolutely right， Okay， so the arrows。

 so the arrows that I drew were stupid。All right， but the idea is sound。So， let's。

Let's take it from the top。So if you're in by the way。

 this is Robin who'll be guest lecturing next week so if you're in Q0 and you see a and you see a zero then you want to stay where you are in terms of the first automaton。

 but you want to transition in terms of the second automaton right so we could say we want you to。

Go like this。 Okay， if you see a one， Yeah， you're right。 So the， so the arrows。

 you have to be careful in writing them。 Okay， I was， I was sloppy。 So， so if you see a one。

 then you want to。You want to move in the first automaton and also， oh。

 and stay where you are in the second one。Which means that。Right。Okay， good。U。Up here。

 what do we do so if we see a0， we want to stay where we are over here and we want to move over here。

And if we see a one， we want to move down over here and stay where we are over there。All right， well。

 you can continue filling it in like this。 Okay， but you see what I'm doing。

 I'm just taking like the product of， you know， this one turned on its side。

 So let's let's draw this one in the appropriate way。呃。嗯。Right。Okay。

Good so the point is that the one arrow here determines you whether we move up or down or whether we stay where we are。

 if we see a one， the arrow over here determines if we see a one do we move left or right or do we stay in the same left。

 right position that we were in before， and then we combine those two pieces of information to get our arrow for that symbol and for that state。

Okay， so that's how it works。😊，It's early in the morning， okay， so any questions about that？😊，Okay。

 all right。Let's do another question。 So so if I draw a bar over L。

 that means the complement of L Okay， and that means the set。

The set of all strings in my underlying you know set like a 01 star that are not an L Okay that's all the complement means all the strings that are not in L Okay。

 so complement is another you know very basic thing that you may want to do to a language okay。

 and so now we can ask the question， if L is regular then is L complement also regular。

Can anyone yeah？Yep， exactly yeah， this is quite an easy one because all we have to do is just switch the accepting and rejecting states and then we're done right like for example。

 here's an automain that recognizes all the strings of odd hemingweight if I if I instead wanted an an automain that recognize all the strings of even hemingweight Oh well you know great now this is my accept now this is an accepting state and now this isn't right so so this is easy。

 okay we'll see examples later where you know these closure properties sometimes are not true or where they're true but they're much less obvious。

 but yes。😊，Oh， so so you know， it works with empty strings same way it works with everything else。

 So like if the empty string is in L， then the empty string is not in L complement and vice versa。

Yeah。Okay， good。All right， so we've seen that the regular languages are closed under intersection and they are also closed under compliment Okay。

 so now here's the next question we could ask。Are the regular languages closed under union？Well。Yeah。

AhThat's a very interesting thought but there's a reason why the fear is unfounded。

 and the reason is that yes， we could build up any language as a union of a bunch of other languages but in general that could be an infinite union and that could lead to an infinite number of states and then we no longer have a finite automaton。

Okay， so in， yeah。Mmhm。😊，Yeah， yeah， you can absolutely do that， you know。

 so that would be one way to answer this。 In fact， another way is that the answer just follows from what we've already seen。

 Okay， you can just because think about it。 What is L union L Prime。 Well。

 by De Morgangan's law you remember De Morgangan's law from last week， it's just。

The complement of the complement of L intersected with the complement of L prime。All right。

 so there we go。The magic of the Morgan， right？And we just got a result for free。See that。Okay， so。

 so let's so we you know， we've seen examples of， of regular languages。

 how to build new regular languages out of old ones。

 actually just following up on the question that that we just had。Here's a quick sanity check。Okay。

 so let's say that a language is finite if it contains finitely many strings。

 only finitely many strings， so then is it true that at least all of the finite languages are regular？

Yeah， how come。Yeah， that's basically exactly right。呃。If your language is finite。

 then all you have to do is just make a big old binary tree where you know you just。

You just create lots and lots of states as needed like this， you know， you start here。

 this is your initial state， you read a zero or you read a one that tells you which leaf to go to and you know since。

We're only interested in accepting finitely many strings we can terminate this tree at a finite number of different possible except states。

And that's really all we have to worry about，You if if say you're here and you know and if you read something where now you've read in a string that's not the prefix of any string that's in the language。

 then all we have to do is you know I can we can just send the automatan to some purgatory where it has to。

 you know， suffer forever or something okay you know and and never accept you know this is not an accept state。

 but there's no possible way to get out of it Okay you know if you don't like that。

 if that sounds to you know。Cruel or something， you know， you can always just you know。

 you can always just draw it like this， right， or just say， you know。

 you know I I just send this automaton off off into space。

 you know you you can just say I send it out to reject because you know we know that you could fill that in if you wanted to。

Okay， so。嗯。So all right， so all finite languages are regular which means you know like the set of all possible you games of chess。

 you know you know that we do a win for white and you know could be played within you know a human lifetime say right that may sound like a complicated set know that's perfectly regular so you know so in some sense like the sorts of questions you know that we be talking about in this course sort of only get activated in some sense。

 you know when we're talking about infinite sets of languages well。

 you know that's not quite true with circuits you know which we talked about last week circuits had the interesting property you know we can take a completely finite problem like you know deciding which player has the win from a given chess position and we can ask the question you know what is the size of the smallest circuit that solves that problem right so circuits are interesting。

even just for completely finite problems， okay， but once we've moved from a nonuniform to a uniform model of computation like finite automata。

 right， you know where the inputs can have any size。

 then then sort of you things only become interesting once we're talking about infinite languages。

Okay，Okay， so an obvious gap in， you know what I've done so far is I haven't given you a single example of a language that's not regular right so you know。

 once again， it's like you see a definition， you see no examples of anything that that doesn't fit the definition you know you know。

 you're just kind of wasting time So so all right so。嗯。So， let's。You know let's try an example。

 so let's say I am interested in the language of palindromes， you know， I'll call that pig。Okay。

 palindrome is just the string that's the same。 You know， red backwards and forwards。 you know。

 famous example is， you know， a man， a plan， a canal， Panama， Okay， or， or， or aba， like。

 you know the。The music group okay。let's just talk about palindromes over you the 01 alphabet。

 so then 01，10 is a palindrome， 01，01 is not a palindrome is the empty string of palindrome。Yeah。

 sure， you know， same backwards and forwards， likewise zero as a palindrome， ones a palindrome。

 0 zero is a palindrome is 01 a palindrome no okay so you know so this seems like you know a very very useful capability for your computer to have to tell you whether a string is a palindrome or not okay so let's design a finite automain that will recognize the set of palindromes。

 the language of palindromes okay well how can we get started doing that。Well。U。Basically， you know。

 you've got a string of some， you know， unknown length。 You start at the beginning。Okay。

 and we need to scan it through from left to right。 And then at the end， we need to know。

Whether the basically just let's， for simplicity restrict our attention to strings of even length。

 Okay， let's start with a simpler problem of recognizing palindromes of even length。 Okay， then。

 you know， in that case， our problem is just to see， you know。

 is the second half of the string the reverse of the first half right， which， you know。

 in in this case clearly it is Okay so。So， so it sounds pretty simple to solve this problem。 Okay。

 all we've got to do is design an automain that just snarfs up the first half of the string。

 stores it in memory， and then compares it against the second half of the string。

 What's the problem with that， anyone yeah。Yeah， exactly， I mean you know， first of all。

 we have no idea in advance you know how long the string is going to be right you know and look。

 you know maybe I'll even be generous to you， I'll put a special symbol in the middle that will tell you when you've reached the middle of a string okay you know。

 even then I claim that there would still be a difficulty。Yeah。Yeah， well in some sense。

 you intuitively there's kind of a problem here which is the whole point of a finite automain is that it has a finite amount of memory it has some fixed number of bits of memory。

 which is namely the base2 log of the number of states of the automain that you could think of is measuring how much memory it has but the amount of memory that it has is not allowed to grow with the length of the string that it's processing and so somehow we want you know some automain with some fixed number of states to recognize palindromes of arbitrary length。

Okay， but， you know， it seems like there's an inherent problem here， which is that。E the。

 the longer the string is the more the automaton is going to need to remember。Right you know。

 because you're going have to sort of remember the whole first half of the string， you know。

 if you want to compare it against the second half， you only get one remember。

 you only get one pass through this thing right so you know。

 but you know it seems like there's there's sort of an inherent memory bottleneck here。Okay， so okay。

 but now you know that's you know， an intuitive argument。

 that's basically an argument that you know like you know。

 I can't think of a way to do it right and you know， and in this course。

 we're not going to be quite satisfied with that kind of argument okay were you know。

 we're not going to sort of you know， sort of insist on sort of you know hair splitting rigor for its own sake。

 but you know， we'll try to make sure that you know we have enough rigor that we don't you know that we we typically don't get wrong answers okay so。

So let's say how to make this argument a little bit more rigorous。

 How can we actually prove that this language of palindromes is not a regular language。Okay。

 so the proof of this is actually going to use one of the deepest facts in。

 in all of math and science。 And that's called the pigeonhole principle。

The pigeon hole principle says that you if you have n plus one pigeons and you're trying to put them into n holes。

 then you know some hole was going to have more than one pigeon， okay incredibly useful fact。

 you know we'll use it again in this course right。In this case， certainly。

 as a special case of the pigeonhole principle， if we had a finite number of holes and we had infinity pigeons。

Then surely， some hole will have to accommodate more than one pigeon。

Okay you you agree with that I don't need to prove that Okay all right well so taking the pigeonhole principle as given。

 let us give a proof by contradiction， so let us suppose that there were a finite automain that recognize the language of palindromes and let us then derive a contradiction。

😊，So what we can do is we can consider the set of let's just start listing all the palindromes。

 all right， I mean there's the empty string， of course， then there's 00， there's 11， right。

 there's say 0000，'s palindrome， there's 01，10， there's 10，01， there's 1111， there's 000000。

And so on， and I'll just split this down the middle。

So we could imagine having an enormous list of all the possible palindromes of every possible length and an infinitely long list。

Now what we're going to do is we're going to say let's let M be our finite automain that we imagine is able to recognize this language。

 you know is able to accept these strings in only these strings。

 M has some you know being a finite automain， it has some finite number of states。

 call that number K say it's K states。Okay well， however big K is I claim that you know okay。

 so now let's what I want to do is I want to just look at what state is the automaton in when it crosses the midpoint of each of these strings。

 this is what I want to do okay so just you know after it's red this symbol。

 what state is it in you know let's call that that state here， we'll call it you know S1， S2， S3。

 whatever it is， you know and each S can be labeled by some integer from1 to K telling you which state it's in now can all of these sis be distinct。

No， why not？Yeah， the pigeonhole principle right， there's only a finite， you know。

 there's only K different states， but there are infinitely many palindromes， okay。

 which means that at some point， you know， the same state has to occur twice in this list。Okay。

 so in other words， know there must be some pair， what we're saying is there must be some pair of palindromes。

Call them- so by the way， by Xt， I'll just mean like the reverse of x， maybe I should call it R。

R for reverse I was calling a T for transpose， but that's more obscure Okay so let's call it Xxr okay so any even palindrome has the form Xxr so what we're saying is there have to be two strings two palindromes。

 Xxr and yy R such that our finite automaton M is in the same state after scanning X as it is after scanning Y。

Right。You know， this this follows from the pigeonhole principle right because there's you know。

 there's just infinitely many choices for the left half of the string。

 but there's only finitely many states that we could end up in after after scanning that left half。

 Okay， So， so say we we end up in the same state as here as we do here， Okay。

 now can anyone sort of finish this off can anyone you know deliver the finishing blow。Yeah。嗯哼。😊。

Yeah。嗯。Mmhm。😊，Exactly that's precisely right okay what we can do now is just splice the two strings together。

 we can make X Y R right or we can make Y Xr okay these strings you know but you know the assumption that X and y are different these strings are not palindromes right you know and yet I claim that M must accept them okay because you know when you know it reads X Y R well you know reads X and then it's in the state S and then it reads Yr but you know we already know that if you're in the state S and you read Yr then you're going to accept so you're going to do it here also yeah。

Well， so I claim that X， YR is never going to be a palnttro。Does anyone see why？Yeah。Yeah。

 that's right。Let's see oh， okay， so maybe。All right， you know， it's easier it's all simpler if I。

 oh you know what， you actually you do raise a good point， which is okay， so this is all all right。

 you know what？Yeah， okay， you know what you're right okay again I'm terrible with details okay but is let's say that theres a like I said before that there's a stop symbol there's a special symbol in between x and y that tells you when you've reached the middle in that case the argument that I gave which is work verbatim if if there's a delimiter that tells you when have you reach the end of x and when have you reached the middle of the string you agree that in this case the argument works okay now you're absolutely right。

 if we don't have a delimiter then there is a technical problem which is that you could have。

 for example， that x would be00 and y would be0，0，00 so there are two strings of different lengths okay。

AndThen these are different strings and yet you cancatenate them， you cancatenate x with YR。

 and you get a palindrome， namely a string of six zeros。

Can anyone think of a way to solve that problem？ I can think of one way that's really， really simple。

 namely。You know， we could simply say， look， you know， by appealing to the Pithole principle。

 you know， you know however large K is， not only are there going to be two x's and y's that lead to the same S。

 there are going to be two x's and y's that lead to the same state s and that moreover have the same length。

Because the length we can just make as long as we want， right， and we can in particular， you know。

 make the length L something such that2 to the L is much larger than than K and then once we do that。

 then we're done。Okay， good， so so this is， you know how you know just just by staring at the language and just by you know giving an argument。

 we can we can give you know a perfectly rigorous proof， you know you know。

 at least if we think about it and we patch the problems we can give a perfectly rigorous proof that that language is not regular so you know we can show in particular that you know there exists non-regular languages。

 you know， not everything that's out there is regular，Now in。Tomorrow's recitation。

YouAnd also in the Siper book， you'll see something which is called the Pumping Lemma。

 which is a humorous name， but all it is is sort of a way of formalizing the intuition that I just showed you okay so it's a way of formalizing this intuition you know about the pigeonhole principle into a sort of a machine that you can just sort of turn the crank without even thinking about it and you just verify that if your language has satisfied such and such properties。

 then you can make a pigeonhole principle type of argument that will show that your language is not regular。

Okay so but you know， when you look inside， this is sort of all that's going on and you know on the PSet there's you know a problem I think to prove you know another example language is not regular。

 okay， and in general， if know we ask you to prove something is not regular。

 you can do it know whichever way you want， you can use the pumping lemma that you'll see in recitation and then Siper's book。

 you know or you could just argue directly using the pitchonhole principle。All right。

So so so we've seen then that you finite automata are actually kind of weak maybe is not such a surprise。

 I mean you know they look weak right but you know like yes。

 you know you can use it to check if there's any ones in your string or if your string has some you know in fact has any designated substring in it。

 yes， you can even check whether your string as an even or an odd number of ones in it。

 but even just checking whether your string as a palindrome you know， you know。

 which seems like a pretty simple program to write you know。

 but that's already beyond the capabilities of finite automata。Okay。

 you know essentially because you know， finite automata can't count right。

 this is sort of the slogan to remember， right， they've got only a finite memory， you know。

 a finite memory can't count to arbitrarily large values。

OkaySo so let's try to come up with a more powerful model。

 okay and there are different ways that you could do that， but there's one。

 well that was invented by Michael Ran in 1959 or so。

 and it was especially influential for the you development of computer science。And。

And this is called nondeterministic finite automata。 Okay， so this was， you know。

 a very bizarre concept when first invented。 Okay， because you know。

 this is a finite automata that's going to be based on the， you know。

 principle that like when you see a fork in the road， you can take it。That you know。

 find an automaton thats somehow you know allowed to explore multiple paths at the same time。

 okay or sort of do you know multiple different things you know somehow somehow at once。

 it doesn't have to be deterministic Okay so so let's let's be a little bit more more formal So so one way to think of an NDFA is that it's like you know that product automaton that I incorrectly drew earlier and Robin caught me like that was an example of one Okay so so an NDFA is basically a finite automain but where you're allowed。

To have multiple arrows emanating from the same state with the same alphabet symbol。Okay。

 so you're allowed to say， you know like if you're at this state and you see a zero then you can either take this path or you can take this one you can either transition to this state or you can transition to that one。

 either one is fine In fact you're even allowed to to have no arrow emanating from from a state with a given alphabet symbol so you're allowed to say if you're at this state and you see a zero sorry you're you're just up a creek there's just nothing for you to do at this point。

 just terminate okay you can do that also okay you can have any number of paths with the same alphabet symbol and including zero and then so then how do we interpret this well the rule is we say that the automaton except if and only if there is any possible path you know consistent with the input that you've seen that leads you。

To an accepted state。Okay，So to be a little bit more formal。

So an NDFA is defined almost the same way as an ordinary finite automain。

 which with retroactively in ordinary finite automain， we'll call， can anyone guess what？

Deterministic finite automain or DFA。 Okay， DFA is the ordinary kind。So I'll say Doctor of Fine Arts。

NDFA， I guess nondo of Fine arts is the kind where you're allowed to have multiple transition。

 so once again we've got a finite set of states， finite alphabet and then we've got a transition function。

That takes as input。A。Okay there's one point here that I want to discuss that so we have a transition function that takes as input。

 basically you the current state and an alphabet symbol。

 and it maps you to a subset of possible states right so it says if you're in this state and you're reading this alphabet symbol。

 then here is the set of states that you're allowed to transition to。Okay。

 so that's what the transition function does。 Now， there's one additional detail。

 which is really just a matter of convenience。 Okay。

 and the detail is that we're also going to allow what we call null transitions。Okay。

 and a null transition just means an arrow that you're allowed to take even without reading any symbol。

Okay so so if we have an arrow labeled by epsilon right then you're you're allowed to just follow that arrow you know if you want to without even you know before you've even read the next symbol you know it's like you know you're playing a board game and like you get to jump for free you get an extra turn or something okay now you null transitions you know we can you know it will follow from things that we prove that they're never actually necessary you can always get rid of them if you don't like them。

 but you know they'll sometimes make you find an automaum more convenient to write down okay so we'll include them。

 so this is just saying that you know you're also allowed to specify a set of states that you're allowed to move to you know even without reading any symbol。

Okay， and then just like before， we've got a designated start state， Q 0。 and we've got。

A set of except states， F okay and then the automaton accepts， you know。

 if and only if there is some path consistent with the input that leads you to one of the states in F。

Allい。So what's the point of all this， this seems like a lot of metaphysical baggage for。

For what end exactly， Well， you know， claim that that you know。

 nondeminism can sometimes make it much simpler to construct a fine automaton that does something that you want。

 So let's， let's give an example of that。 let's see。嗯。诶。Okay。

 let's consider the language consisting of all x's， such that the third， the last bit is a1。Okay。

 so that's， you know， now you say you know， is this a regular language， you know。

 is this not regular， well， you know， okay， I claim with。With enough effort。

 you could design a DFA for this language， you know I could leave that as an exercise for those of you who are interested。

 although it will sort of be trivialized by the end of this lecture but you can do it you can design a DFA for it。

 It's not quite obvious how to do it because after all。

 how do you know when you've reached the third to last character you're just reading things one by one。

 you don't even know whether the character you're now reading is the third to last so you could imagine that you deal with this。

 you maintain a buffer of characters， you know and so that at any point。

 you know if it so happens that you've reached the end of the string then at that point you still remember what was the third to last you could imagine doing that by maintaining a buffer and then constantly just throwing bits out of the buffer if they're if they're not among the three that you saw the most recently right so so that's that way you'd only be maintaining a finite amount of state。

At each point in time， So you're still a finite automaton， you know， you。

 but you you'd always be remembering what was the third to last character that you saw。 Okay。

 so that's a way you could do this， you know， but it's a little bit complicated Okay， now you know。

 how could we design a nondeterministic finite automain that does this more simply。Anyone。Oh。

All right， so let me get you started， so we'll have an initial state Q0 and you know I'll say you know if yourre reading is you know。

 no matter what you're reading， you can always stay in this initial state as long as you like。

 that's fine okay and then what's going to happen。啊。Well。Okay， at some point when you see a one。

 you're allowed to go over here Okay， again， you know。

 we've got two arrows both labeled by one emanating from Q0。

 but that's fine we're an NDFA okay then what do we want next？Well。Yeah。嗯哼。Yeah， and。いや。Yep， yep。

 so this is the accepting state and。There we go Okay so I claim that this should work for us right because this is saying。

 you know now the question is under what conditions， you know。

 will there exist a path that leads to the accepting state right Well。

 you know what does a path have to look like it can hang you know it can just waste time you doawt all around here as long as it once。

 but Dan at some point there's got to be a one in the string and then there's got to be two other things in the string right so at any rate the third the last character has got to be a one and any time the third the last character is a one then there will be a path that like this that ends at the accepting state All right。

 so good， so that's our endDFA。All right， so now you know， the type of question that， you。

 we'll sort of train ourselves to immediately ask in this course when you know we encounter a new notion as well。

 you know， is it equivalent to the notion that we saw before or isn't it？呃。So。Sorry。Okay， so。

So I could loosely phrase that question as does NDFA equal DFA you know this is going to be like our first baby version of the P versus NP question okay you know。

 and the first thing people like to say as well you know so you know if n is one。

 you know if DF a or zero you know okay but let's try to answer this for real， so。So actually。

I claim， and this is kind of surprising and kind of interesting if you've never seen it before。

 that everything that can be done by an NDFA can also be done by a DFA or to put it differently。

 the set of languages that can be recognized by an NDFA is precisely the set of regular languages you know the set that we already to find so we don't gain any new expressive power by allowing nondeterminism you know it might make our final autotmas simpler to construct but it won't let us recognize any languages that we're literally not recognizeognizable before okay so how do you think we could prove this。

SoWell， you so the outline is is pretty immediate， right， what we want to do is we want to。

Start with any NDFA and then construct a DFA that simulates it that does the same thing that recognizes the same language。

AllI mean， I guess the first thing we have to say is yes you know you know with most of these things at least there's one direction that's pretty obvious right if you had if you had a DFA you know then certainly you could construct an NDFA that does the same thing because well。

 just take the DFA that you had that that will count by the way。

 you is you there's a principle that I'll sort of appeal to many times in this course。

 know I call it the Superman principle you know if your Superman。

 you can always at least simulate Clark Kent you can always just sort of ignore your superpower and just do the thing you would have done without it so in this case if you're an NDA。

 certainly you can simulate a DfaA so the interesting direction is the opposite one know how can we take an arbitrary NDFA say M know let's say that has K states and now we want to。

It by some DFA with some other finite number of states。Okay。

 so you know so it's not obvious right because the you know NDFA is able to you know have all these transitions going on at once。

 it can be some sense following all these different paths at once， but you know。

 but if we were trying to just maintain the state of our NDFA by just a deterministic finite machine。

 like like what information is it that we would have to remember。

 let's come at the question that way， yeah。Exactly， exactlyly yeah。

 so the key idea here is that we're going to take an entire set of possible states in the NDFA and we're going to you map that onto a single state in the DFA okay so we'll have one state in the DFA that represents this set of all the states that we could have possibly reached at this point in time if we were in the NDFA okay。

😊，So this is called the power set construction。 and what it's going to do is it's going to take in an NDFA with K states and it's going to produce a DfaA with two to the K states so there's an enormous blow up here in the number of states and in fact one can prove you know I'm not going to do it。

 but it's interesting to prove that this blowup is is unavoidable so there are NDfas that can only be converted to Dfas you know by exponentially increasing the number of states okay but know what's an exponential increase between friends right where you know you know the result is still going to be a DfaA with some constant finite number of states you know so we' prove the language is regular So we're happy okay so it's probably you know so like you can read in SP or you know he writes out a full formal proof。

You know of the power set construction and the fact that it works。

 it's probably easiest just to do it by way of example because you know， once you see an example。

 I think the idea is clear， so let's do this one here。You know。

 and just to make things a little bit more manageable。

 let me say that you know what we were actually interested in was the。The set of all this。

 the strings where the second to last bit was a one。 All right， good。 So I've just。

I've just trimmed this a little bit。Right。Okay。Okay。

 now the idea with the power set construction is that we are going to。

Have one state for every possible subset of states of this NDFA right and not all of them might turn out to be relevant。

 but let me just write them all down anyway first of all so one thing it's not I guess it's not two to the k it's actually2 to the K minus1 because I don't actually care about the empty set never're gonna to have an empty set of states right so let's just start with you know I could be in 0 you know by which I mean Q0 I could be in1 I could be in two。

 I could be in 01， I could be in02， I could be in 12 or I could be in012 and each of these represents like the set of states that you could have reached you know at this point in time if you you given the section of the input that you've read so far so so now let's fill this in。

you were in state Q0 in this NDFA， and you read a zero， then where can you go？0ero。if you read one。

 then where can you go？Well if you read one， you can go to zero or to one you have two choices which means that the one arrow and there has to be only one one arrow over here because this one's a DFA。

 that one is going to go over to01 right okay if you're in state you know what let you know skip this you know some of these states are never going to be reachable anyway so we don't even care about them let's say that you're in state let's say that you could be in state zero or in state1 and now you read a zero now where could you be。

Well， if you were in zero and you read a zero， then you know you're going to stay in zero。

 if you were in one and you read a zero， then you're going to be where。2。

 which means that now you could be in zero or  two。 Okay， if you are in。

If you were in zero or1 and you had a one， then now where can you be？

Now you can actually be anywhere， can't you， Yeah， you could be zero， one or two。Okay， and so forth。

 So we fill in a thing like this。 people understand that。So okay。

 and then what should our accepting states be？Yeah。

 accepting state should be anything that contains it too。Yeah。Exactly。

And what should our initial state be？Our initial state should just be zero right and I can sometimes I'll write that just by drawing an arrow that comes in from nowhere with an epsilon transition so yeah。

 so the initial state you where we start and stayed zero and then you this models everything that happens。

Okay， so。You know， and notice already that this， you know。

 this lets us deduce things that are not you know entirely obvious like for example。

 let's say that I just first showed you the definition of an NDFA and I had asked you， are you know。

 take the set of languages that's accepted by NDFAs now is that language closed under compliment？

Okay well， you know， it's you not obvious right， you know， given an NDFA。

 how do you construct an NDFA that accepts the compliment know of what the first one does right well it's not clear。

 but you know one one way to do it is well at any rate。

 you could just convert that NDFA to a DFA and then take the complement of that。All right。

There's one more thing in this in this。Happy family， I guess， of computation models。啊。

With which I'll finish the lecture and that's the regular expressions Okay， so you know。

 those of you who have done you know， any programming any you know compiler stuff， you know。

 you've probably or even just you know used you know decent text editors。

 you've probably messed around with regular expressions in the past they're they're very。

 very useful they are。Basically there are ways of you know specifying sets of strings okay so in other words languages okay and they are built up out of a few symbols like you have some alphabet you know of basic letters like in this case。

 let's say there's zero and1 and then you're also allowed to do concatenation which means you know if you have any two regular expressions。

 you can just put one next to the other， which know and I normally won't even write the concatenation symbol because that just means just put two things next to each other and you're also allowed to have an or symbol。

 which means you take either this or this then you're allowed to have what's called the star symbol which means take you know any number of copies of this thing that I've starred know that you want including zero copies okay。

And then you're allowed to have parentheses， so you're allowed to nest expressions， you know。

 recursively inside each other， and that's all you're allowed to do。Okay。

 so let let's do some examples so like let's say that you know you had a picture of a sheep you know in your computer and it was called you know it was either a JPEG or a GF file you can't remember which okay。

 and it was called Ba dot， whatever the extension is。

 but you can't remember how many A's there were in the B okay。

 so what would be a regular expression for searching for this file。Yeah。Bstore do。Yeah。

 that open parenthesesis， Jeff。Po Jpeg。Okay right and you as they said。

 you know any decent you know file search utility will actually let you do stuff like that。

 you know Google also lets you use regular expressions right so you can do more sophisticated searches that way。

Good。So， so let's， let's now just。Let's do another example。

 what would be a regular expression for the language of all the strings that have either a 000 or a 111 somewhere in them。

 yeah question。Oh， okay。 so yeah， you're， you're right。 You you know， you， you can。

 you can add all kinds of things that， you know like would， would， you know， would。

 would would be would would make things more convenient for for ourselves。 right， if， I I claim that。

 you know， if， if you wanted a symbol for one or more copies of this。

 then we can actually just simulate that using the star symbol only how how would we do that。😊，Well。

We could always just do something like this， right？You know so I say。

 look take the one copy and then take as many additional copies as you want。

 including zero All right， so I'll just stick the star but you know if you wanted to use plus you know。

 to mean like one or more， you know like when you do your piece or midterm， it's okay。

 just maybe just put a note to just you know make it clear to the greater that it's what you're doing okay。

So so all right， so let's just stick to to these symbols for for the lecture。

 I guess so how could I write a regular expression that says you know there is at least one you know。

 substring and my string that's 0，0，0 or 1，11。You know， let's say that my string is just though。

 you know， a string of zeros and ones， yeah。Mmhmm。😊，Yep， excellent。Good。

 so there's a nice example of a regular expression。

 which you picks out the set of all strings that contain you know either this or this as a substring you know。

 and on this this here I should。And all this this stuff at either end is just to say that before and after the substr。

 you're allowed to have whatever you want and as much of it as you want Okay。

 that's all we're saying。 All right， All right， so let's do a more interesting example。

 what would be a regular expression that picks out the set of all strings of zeros and ones that have even parity。

Who hasn't spoken yet？Vi。Okay， cool。Yep， what？Okay， let's start out by looking at that， so 0。

0 or 01 or 10 or 11 star Okay， so that's certainly a valid regular expression now does it give us all and only the strings of even pary？

No， okay， so what can anyone give an example of an even parodity string that's not caught by this one？

Oh， right， okay first of all， I guess what this is actually giving us， yeah。

 is the set of all strings with it of even length。RightThis is giving us all the strings of even length right so in particular。

 know this could in the first place， you know， this could give us strings of odd pary like this one。

 and there were also strings of even parity could that this would not give us such as 011。Okay。

 so it's a little bit trickier。 you， yeah。Zero star one， wait， zero star one， and then sorry。This。

 this almost does it。 Can anyone see， you know there's one little tiny issue with this one。

 Can anyone see the little what？Ha。Yeah。Yeah， yeah， this one doesn't catch the string of all zeros。

 How can we fix that。Yeah。There we go there there's our set of all even hemingweight strings Okay。

 and you know you could have fun writing one for the set of all odd hemingweight strings Okay and you know there you know there should be some PSet problems about this okay but。

You know one thing you know you notice is okay we were able to write a regular expression for the set of all even having late strings。

 we were also able to you know write a DFA for that before right and in general you know the things that we're able to write regular expressions for seem somehow related to the things that we're able to you know give DfaAs for so you know we could write Regg X for just you know the set of all the languages that can be specified using regular expression and you might wonder about the relationship between this and and these guys okay so what you're going to see next week is you know the amazing fact that actually regular expression equals these two guys okay so just another way as its name might suggest of picking out the same happy family。

 the family of regular languages okay and then you'll see a further。Notion。

 which is the context free languages。They're mostly in the art department。I mean， in film。

 my girlfriend's in film and that's what she tells me and she used to be in the art department but now she's mostly directing and writing stuff just came from the arts departments like journal？

Yeah it is very artistic， that's what we learned I tried to get TAs once to do videography。

ItsUn you have the aesthetic， it's really tough yeah， and practice of course helps but。For my dad。

 he basically jumped into it with almost no experience。

 he just had the eye impressive he's hard to replace be excited that's true Yeah care about the lecturer true and all the life。

YeahYeah。right go you have Oh， I have。さ。I wanted to tell a videographer something。

 I have a surprise for today's lecture。Which are some temporary tattoos。

SoJust putting that out there at some point you might want to zoom in one of you or something。

Something funny doesn't have to be super zoom， should be pretty visible， that's to the intense。

Which arms both arms I have I'll do one and then the other。So。My camera。Yeah。

I mean we don't have to get super close。