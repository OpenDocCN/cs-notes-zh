# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p05 P5 Lower bounds via compression arguments. -BV11zi7BjEHu_p5-

![](img/150909d6661a64660cb147ea96288e02_0.png)

Okay， so today， as I promised， finally， we will start talking about lower bounds。

🤧And I actually already put the notes for today on the website so you can take a look after lecture。

IIt's section 3。1。And I will you know I want to talk about general techniques for proving lower bounds。

 of course I will apply these techniques to specific problems so you can see them in action today you're going to see the compression based idea for proving lower bounds applied to both the distinct elementss problem as well as to the quantiles problem so two problems that we've already seen in class。

So let's get started。嗯。So there are a few different techniques。So for example。

 there's the compression based arguments。And two， there's whoops。Let's say communication complexity。

And you know these these are not actually they're not necessarily I guess disjoint techniques。

 I mean in fact some some communication complexity arguments。

 the way you carry them out is via a compression based argument。

 so there is some overlap between them， you don't know what these terms mean yet because I haven't told you。

 but these are two not necessarily disjoint techniques that are commonly used to prove lower bounds。

For sketching algorithms。Today we're going to focus on specifically compression based arguments。

And this is my terminology， I don't know if you'll find。You know。

 this categorization written anywhere in any textbook or in the literature。

 communication complexity is a term that people standardly use。

 saying that a lower bound is a compression based lower bound。

I say that's my terminology what do I mean by that what I mean is you know we're going to basically we're going to prove。

We're going to approve。Theorems of the following sort。😡，Arguments of the form。You， suppose。

There exists。You know a sketching algorithm。A for some problem like distinct elements or quantiles。嗯。

Using S bits of memory。Then there exists an injection。F。Mapping subset S。Not S。

 let me not overload there。Mapping subset， let's say call a Q into let's say01 to the S and it might not necessarily be01 to the S。

 you know， it might be。01 to some function of s01 to the root s or whatever。

 but basically there's an injection mapping some set into some bounded set so right01 to the ss size2 to the S so it's mapping Q into some bounded set。

You know， therefore。You know， you cannot have a bigger set you cannot have an injection from a bigger set into a smaller set。

 so therefore。The set Q has size less than or equal to the size of the right hand side。

 which is two to the S right therefore two to the S。嗯。Is at least the logarithm of Q。

Or in other words， S is at least， you know。This should have been the size of Q。Or in other words。

 S is at least log based2 the size of Q。ok。Now there can be a lot of。

 you know cleverness in how you get。And how you actually carry this out， you know。

 how do you actually prove that the existence of a good algorithm implies。😡。

Implies that there's this injection。 How do you identify what Q should be， That's kind of the art of。

Proving such things and sometimes they can actually get quite complicated this carrying this kind of thinking out and you'll see today you know our very first argument。

 compression based argument for distinct elements will be a very simple argument。

And then the kind of the next arguments that prove stronger lower bounds will get a little more sophisticated。

 not too crazy。There are humans out there that are even a little bit crazier。Okay， so let's。

Let's proceed。So we're going to apply this to both distinct elements as well as quantiles， as I said。

 so example。Distinct elements。So remember what distinct elements is you see a stream of indices， I1。

 I2， IM， which are each in the interval from one up to n。嗯。

And if you remember the algorithms that we talked about in class were both randomized and approximate。

 right so in class。We showed that， you know there are。Space efficient。Algorithms。That you。

 randomized algorithms。That output。T tilde T， let's say T is the actual number of distinct elements in the stream。

 T tilde is the algorithm's output， which is trying to approximate T。

That I have what T Tilda such that， the probability。

 the probability is over the internal randomness of the algorithm。

 the probability that t minus t tilde is bigger than epsilon t in magnitude is at most delta。Right。

So， you， there are some natural questions here。You know， I'll say。1。Is approximation necessary？

And two。Is randomness necessary？唔且。😊，And， you know， so for example。

 when I say is approximation necessary， what I mean is like。

 could we hope to have a randomized algorithm？Okay。

 which with probability2 third outputs the number of distinct elements exactly。😡。

And with probably one third might fail to do so， and when I say is randomness necessary。

 I mean could we have a deterministic algorithm？Which is always guaranteed to output the number of distinct elements to within。

 say 10% error。😡，And also we want this algorithm， of course， to use sub linear memory。

 wanted to use very small memory。And the answer to both of these questions is。Yes。They are necessary。

To both questions。And the proof of this is actually back to 1996。Alone Maius insgeti。Okay， so I will。

 I will， we will see the proof of。Of this today， okay， and more。So let's just do a warm up。

And it's a good warmup because we're going to use some of these ideas and the actual lower bounds。

 the more sophisticated lower bounds。And this will be this warmup is a compression argument。

So theorem。let's see。Suppose。Scrip A is a。Deterministic。And exact。Algorithm。For a distinct。Elements。

Using。Ask bits of memory。Then S is at least n。Right。

I'm saying here that the elements in the stream come from a universe one up to n。

So this is really saying there's absolutely nothing non trivial， I mean。

 you can always just maintain a bitter array of lengthed。😡，And solve distinct elements that way。

 right， So this this theorem is saying there's there's nothing that's even。

Minutly non trivial into the space of deterministic exact algorithms for this problem。切。

So let's prove this。And remember I said we're going to show that the existence of such an algorithm implies an injection。

From some big set into some smaller set whose size depends on S。嗯。Well， so。

That there exists in injection。Which I'll call ENC stands for encoding。

So the injection is an encoding that maps。Elements of 01 to the n into elements of 01 to the S。

And this， of course， if it's an injection that implies that s is at least added。Okay。😊，So。You know。

 ENC is just a function， you know， I don't really care that any of this is algorithmic right because at the end of the day i'm just trying to prove。

This lower bound right against the memory， it doesn't matter that the injection is efficiently computable or anything like that here it will be but you know in general that that's not required to make the proof go through。

So let me tell you how this encoding works。So。Suppose we're given。Some x， which is in01 to the n。

You know， we can interpret。X as a set， what I'll call let's say capital x。

 which is the set of all I such thatxi is 1， right？That little x size one， so capital x is the set。

 little x is like the indicator vector of the set that just tells you which things are in the set by putting a one there。

Okay， so。What is our encoding wing to do？So。How does the injection work will artificially。Create。

A stream。Containing。All I in X。Okay， then we will run。Scrriip A on the stream。Then the encoding of x。

Is。The memory contents。I was script A。Does that make sense？Whats the listening small eggs and big X？

So we're definingying an injection， I mean， I could have just defined I guess I could have just defined the injection from the power set of one to n。

 but little x is an element of01 to the end， so it's a bit vector of length n， capital X is a set。

It's the set of all I such that little X is one right so if you have a01 vector。

 you can interpret it as a set right you can interpret as a subset of one to n。

Just where the ones are tells you what's in the set zero means it's not in the set。😡。

Does that make sense？Yeah。So。Right， so just to make sure we're on the same page。

 let's say that little x is the vector， you know，1，0，01。 and of course this is right here， this is。

Coordinate  one， coordinate 2， coordinate 3， coordinate4。

Then this leads to capital X being the set14。Which leads to the stream。Being one and then four。

Okay and then we're going to run script A on this stream， okay。And。Kind of what is， you know。

 what is really what is like an algorithm you can think of an algorithm as or you know， what is it。😡。

How do I describe the run of an algorithm？You know or the state of an algorithm I mean an algorithm basically just has some controls which is like the code used to define the algorithm and then also its memory state right and its memory state I told you is an S bit string it uses S bits of memory so you know this this algorithm it's running on the stream it's maintaining some memory which is S bits now we're done with the stream I can just take the memory contents and that's an S bit string so that that is my encoding that's what I map X to。

系。And what does the decoder do right okay， so you know。

 I need to convince you that this this this function is actually an injection right just to make sure that we all on the same page here injection just means。

😡，X not equal to y implies right f of x is not equal to f of y it maps different things to different different things in the domain to different things in the range。

 so I need to convince you。That if x and X prime are two different strings then their encodings won't be will not be the same the memory contents of the algorithm have to be different for different strings that's what we need to show I mean isn't that just by definition of having an exact algorithm so well no well I mean it's not going to be that complicated but you do have to argue something right because when you query the algorithm the algorithm does not give you X the algorithm gives you the number of distinct elements。

😡，Right。So like for example， let's say here I gave you the string， I gave you the vector 1001。😡。

What's the number of distinct elements after you run a on it。

 it's two right in this but I guess like if I have if I have two different。

 if I have two different streams that have the same memory contents。

 then the algorithm cannot be outputting different answers。

 even though the distinct elements are different， right？😡，I sorry I said again。

So like if I run my algorithm on， you know， let's say we ran difference this thing instead， one100。

the algorithm for both of these， it's going to say two， right？I see。 Yeah， okay。

 but that but you know， that's so that's。Then that's that's not it's not clear a prior I mean there is a simple argument you'll see in a second。

 it's not clear why these two vectors you know need to have different memory footprints for the algorithm because the algorithm can say two for both of them。

😡，Right so as long as the memory is telling the algorithm， say too。know what's you know。

't why can't that be true？And you know， the number of the answer is definitely a number between zero and n。

 right？Because we're we're only talking about end bit vector end length vectors here。

 so this basically the number of distinct elements is the support size of the vector or like the number of ones in it right which is a number between0 and n I can represent a number between0 and n using basically log n bits So why can't I get away with an algorithm that only uses log n bits It just needs to remember。

The answer right and so that's what I'm going to show you now I'm going to show you that in fact。

 the algorithm needs to use end bits。And the way I'll do it is I'll show you basically an inverse。

 I'll show you that there's a you can invert the encoding and get back X exactly。😡，Okay。

So since it's invertible， it must have been an injection。So here's theversion the inversion function。

 which I'll just call the decoding。So。The decoding takes as input， let's say M。

 where here M is like the memory contents。So it's an SB string。

So the first thing I'll do is I will initialize the algorithm with that as its memory。ok。

And then what I'll do is I'll ask， what are the number of distinct elements？

So I'll say S is equal to a dot queryery。And then I'll initialize my return value x to be for now it's going to be the all zeros vector。

 but I'll gradually add some ones into it as I discovered ones。And then I'm going to have a for loop。

For I equals 1 to n， I want to determine is Xi 1 or not。

So what I'll do is I will append I to the stream， so a dot update。A。Right。And then what will I do？

Then I'll query A。OkayRemember this is an exact deterministic algorithm。

 so tell me right now what what are the possibilities for R？😡。

The only two numbers R couldB right now。It could stay the same or it could be they could have increased by one Yeah。

 exactly it's it either stayed the same or it went up by one Now when do those happen， basically。

 if this is the first time I'm seeing I in the stream， it'll go up by one。

But if it was the first time I'm seeing I， that means Xi had to have been zero。

 otherwise it would have been inserted into the stream by the encoder。😡，So basically， Xi is1。

 if and only if R did not go up。😡，Okay， so if。R didn't change， so if r is still equal to S。😡。

That means it must be the case that Xi was1。Then I'll set Xi to be1。

And then now I'll update S to be what R is。And then down here I return X。Okay， so that's it。

So this indeed， it's something that's not too complicated。And I'm just showing you here that。

In fact the encoding is invertible right let me not be pedantic I mean I hope everyone is under you know understands let me know if you have a question。

Why this thing works right it's just you item by item or index by index trying to figure out whether or not that index already appeared in the stream of the encoder。

😡，And it's able to do so exactly。嗯。Yes， so there's a question from Edward if we have that M is much less than n。

 then can't we just store the numbers we see using m times log n bits and that's true so but if you notice in this proof。

What is the length of the stream M？😡，The length of the stream M and this is at least n and it's at most2 end。

Right， so this， you know， so I guess I should qualify。😊。

Suppose A is term as an exact album for distinct elements using aspects in memory， you know。

 on streams。Let's say on streams。Of length。You know， Oomega n。Right。

Because in our lower bound indeed， as you point out， Edward。

 you know you need the length of the stream to be。To be linear if you want a linear lower bound。

Any other questions？Okay， sorry， quick。 So if R is equal to S， you set X I to one。

But that's because you know that in the original Xi， it's equal one， right？

I'm just confused Yeah right X X is the thick So right the decoder doesn't know X the decoder is trying to figure out what x is right So initially。

 you know he just sets all the entries of x to zero and then one by one。

 he tries to figure out whether that index was actually a one And and yeah so does that I don't know if Im I'm just going I just mean the X size there's a you say if R is equal to S it says X is is equal to one that means like in like the original Oh yeah yeah。

 yeah that's right that's all I man。And yeah。know，For the vector that was encoded。

Not for the X earlier in the pseudocode。Okay。Okay， thank you makes or maybe this will make it clearer。

Okay， that works okay， any other questions？Yeah actually I have two so the first one is can you go back to the previous slide so so basically the issue in this example that you drew was like if the algorithm had the same memory contents after you know one4 and one two then if I take those two outputs and then I queried again or if I input again to and then I or if I again input four then at least one of those would have stayed the same and then there would have been an error right。

If I I there wouldn't wait， there would not be an， oh an error you mean it wouldn't give the correct number of distinct elements as that way。

 yeah， exactly。Right， so I guess the point is let's say for those two different streams in one of them if you inserted four or let's say if you inserted two then the number exact wouldn't up in for it would that's right yeah yeah and then and then my other question was so what you had said before about the length of the stream is it the length of the stream that matters or the like the possible like the possible integers like we have integers one through n it seems like it seems like what matters I mean both because there is there is an algorithm that uses memory big O of the min。

Of M log N。And add， right？Like both。Sorry， what is little M here M is the length of the stream Oh okay。

 okay， yeah right， so you know， this lower bound needs to make an assumption about M otherwise you're not you're not going to get an omega n lower bound otherwise。

I mean really what you can say is actually this lower bound here is actually proving a lower bound of omega the min。

Of M and N。Right。You can view it that way as well because you can say， look。

Suppose that I tell you that。I want a lower bound for streams of length M。Over a universe of size N。

 Okay， well if。If M is much less than n。Then what I can do is I can just run this argument and not use the last part of the universe。

 you know what I mean， I can just I can just encode strings of blank M。😡，Yeah。😊，嗯。

And I would still get I would get an omega M lower bound。Okay， any other？Any other questions？Okay。

 so let's move on to something a little more sophisticated。Um。What about？You know， deterministic。

And approximate。Algorithms。Is that possible， can I have a。

10% approximate you know it's guaranteed to always give me a 10% approximation with probability one it's a deterministic algorithm is that possible and it turns out that's not unless you again you use omega n bits of memory and I want to prove that but before I can prove that I'm going to need to take a little bit of a detour and talk about error correcting codes。

😡，ok。So definition， what is an error collecting code？系。嗯。A code。It's just， let's say， a subset。Of。

Let's say call it Q to the L when I say， when I say like bracket a。

 what I mean is the set went up to a。And。嗯。Just some terminology here。Q bit you。

 thank you is what's called the alphabet size。Just's give me one second。L。

Is what's called the block length this is just this is just jargon in the field kind of standard。

Standard jargon in when people talk about aircrafting codes。

Let me define something which is the hamming distance。

The having distance between two vectors x and y。It's just basically the number of entries where they differ。

嗯。The distance。Let's say D。So the distance of the code is basically distance。

 the handling distance between the two closest elements of the code。So this is。

 let's say the min over x not equal to y in the code of the haming distance between x and y。

And let's say little D。Is the relative distance。And here I'll call， you know。

 the relative distance between two code words or between two vectors is just the distance normalized by the length。

So this is just D overl。So。You know， a。A code is just a collection of vectors。

 usually those vectors are called code words。So and each one of these code words is just。

 you can think of a string of length L where the symbols。

 the alphabet are they're basically a Q sized alphabet。

 so the symbols are numbers between one and  Q integers between1 and  Q。😡，And an observation。

Suppose I take a code word。From the code。And， you know， arbitrarily change。Less than。

 let's say D over two of its entries。To obtain a corrupted version of it。

And I told you I did this so you know。嗯。I didn't tell you which entries I changed。

And I didn't tell you， I didn't tell you what C I started with。

 I didn't tell you which entries I changed and I didn't tell you what I changed them to All you know is I took some code code word and I did this I arbitrarily changed less than capital D over two of its entries to obtain a code word。

😡，Then I claim that C is uniquely determined。In other words。You know， a third party can then come in。

 look at C Tilda and uniquely decode to figure out what C was， okay， and why is that？😡。

You know having distance is a distance and you know it is a metric so if you have all these different code words。

 so let's say this is c1 in the code， this is C2 and this is you know C3 etc。Draw balls， you know。

 hamming balls with of radius。D over two about them sorry D was the minimum distance of the code in the code word right it the codes right that's right yeah yeah so。

The， there are no two code words that are less than D apart。O。

Every pair of code words is at least de apart in hamming distance。So this is the picture。

 I'll draw balls of radius。D over two here。AndI'll draw another ball here radius D over two。

 all these balls are radius d over two。So here's a question， you know。

 so now when I I basically when I corrupt and I told you I corrupted less than0 over two of its entries。

When I corrupt， I get some。I got some C Teldo， which is like the corrupted version of C2。

Could it be the case that？Okay， so first of all， what should the decoder do？

The decoder knows what the code is， so he knows what all these Cs are。

 so he'll just draw these balls and he'll just return the C such that seat Tilda is in its ball。😡。

OkayWhen is the decoder going to run into a problem？😡。

They're going to run into a problem if C Tilde is in two such balls or more than one such ball。

 so can it be the case that C Tilde is actually in multiple such balls？😡，Can that happen？

No by a trilineality by tri exactly right by a trilineequality this is impossible so you know you know that if it's in if it's in C4s ball。

 this is at most D over two。And you also know that， again， this is at most De over two。

That implies that the distance between。C2 and C4。Is less than d over  two plus d over  two is less than D。

 which is a contradiction。Okay， should the distances and see totalddle to the codes be strictly less than the over two。

 Yeah， strictly less than the over two。So if I corrupted。

 if I took a code where and I corrupted strictly less than D over two entries capital D over two entries。

 then a decoder can come along and uniquely figure out what the original C was that's the claim right and it's because of this because of this picture right here。

😡，嗯。Okay， and and by the way， I mean this this is why they're called error correcting codes。

 I mean the idea is。😡，You know。Let me， this is a little diversion from what this course is about。

 but you know there are entire courses on errorrypting codes and textbooks on errorrying codes and。

Journals on them you know why are they why do people care about them and they care about them because because they want to do error correction right so the idea is。

😡，Of error correction and more generally。Is that， you know？Alice wants to send a message。

Let's say let's call it M， which is let's say a qubit message。😊。

And you know there are many different ways Alice might want to transmit this message。

 the message could be a song， you know， some digital recording of a song and Alice wants to burn it on a CD or the message is going to be sent you know over the internet over over a wire through you know。

 or maybe it's over the phone right Alice is talking and speaking the message。😡。

And CDs can be scratched， right？Phos can have static on them。

 phone lines can have static on the internet， you know。

 my connection might drop a couple packets here and there or something。And the point is even。

With these kinds of， you know， corruptions of Alice's message。

 I want to make sure that the person or the people at the other end can uniquely recover exactly the message that Alice sent。

对。嗯。And that's basically what。Aircrafting codes allow you to do so the idea here is you know。

Alice's message。So first of all， what I'll do let's say is。As follows。I'll pick an injection。

Let's call it ENC for encoding。Which maps？0ero1， oh and sorry。

 I didn't mean to say Q because I said Q is alphabet size， so let's give me another letter B。

It maps zero under the b into。😡，The code。Meaning that each different message that Alice might want to send send corresponds to a different code word。

😡，And what Alice does is Alice actually transmits。Not her message， but the encoding of her message。

Right。And as long as the channel that's another kind of jargon word that people use in coding theory。

 the channel is the medium by which she transmits the message。

 so it's the CD or it's the phone line or whatever medium is being used。

 as long as the channel doesn't corrupt too many of the entries in Alice's message like it corrupts at most D over two of them or less than D over two of them。

Then whoever is on the receiving end can decode and recover M exactly， right？

So less than D over two corruptions。In the channel。Implies。嗯。Can becode。More specifically。嗯。😊。

If they're， you know， what the decoder will do is they'll be able to correct the errors and get back the actual code word that E sent。

😡，And then now that they have the actual code word， they can inverse the injection。😡。

To get back to the original bebit string。Okay。So that's that's why they're called error correcting codes for us kind of we're just going to more look at them as。

For our lower bounds purposes， a collection of vectors that have large pairwise distances okay I mean we actually are going to think of them also as you know。

 things that can be decoded or corrected。嗯。So we're going to use these now before I start using them to prove more lower bounds。

 any questions。And I way I should mention， you know， this person this。I this， by the way。

 I didn't write it， but I said it this is called。Haming distance。

And it's named after Richard Hamming， who was one of the early people in the study of air collecting codes。

And。嗯。😊，There are kind of two main threads I would say that people study and coding theory of how you know how how to treat the whole topic of error correction。

 one is kind of the hamming model where some adversary comes and corrupts arbitrarily some fraction of your code word。

😡，Okay， that's the heing model。诶。😊，Then there's the Shannon model so Claude Shannon is kind of the other school of air correction and there you imagine that your channel is actually stochastic so it's not that。

It's not that a worst case adversary comes and you know。

Tries to choose the D over two entries to corrupt to screw your decoder as much as possible。

 no rather there's a stochastic channel that corrupts the code word in a random way。😡。

And you know there are lots of different kinds of stochastic channels that people study one common one is each let's say let's say that the code words are actually bits so Q is two right so the entries and the vectors are zero and one so there's something called the binary symmetric channel or basically for each bit independently。

The channel corrupts it with some probability P， otherwise it leaves it the same。😡。

So it flips it with some probability， otherwise leaves it the same and then now what you want is to be able to decode with high probability。

 right？So anyway， just something that I thought I would mention。TheThe other。Model。

 if you want to read it on this on your own or take a course， you know。

 if you're motivated to take a course on it later is the Shannon， basically Shannon。Shannon coding。

Good， so let's get back to now lower bounds。And I guess before I okay。

 so before I use these objects to prove a lower bound， there's a very natural question here。

 which is。Do good error correcting codes exist？😡，So I what and defined what a code is， you know。

 do they exist？Now， kind of what？What does it mean now for a code to be good and when I say to good codes exist。

 what do I mean by that？😡，So， let's say that。You know you fix you know you fix the alphabet size。

 I mean you can basically fix a bunch of the parameters and kind of let the other parameter not be fixed and ask how good you can get that parameter so let's fix the alphabet size to Q let's fix the block length to L。

😡，And let's say I know that I want distance capital D。😡，Okay。

So that basically determines all the parameters here。😡。

What's the only other parameter thats that's left and kind of what do you think it means for that parameter to be good？

Any cardinality of the code right Yeah exactly the cardinality of the code itself。

 so I know that you know the biggest it could possibly be is Q to the L。So I would love to have。嗯。

alphabet size Q， block length L and Min distance capital D。And have Q to the L such code words。

 I want this code to be as big as possible why because remember。😡，At the end of the day。

The whole way my encoding works is there's an injection from the space of messages I want to be able to send to the code。

😡，Right， so you can think here basically that B is。😡，Log base two of C， the size of C。喂。I mean。

 let's say it has to be an integer so let's say it's the ceiling of this。

OrNo it has to be an injection， so other way around， the floor can't be bigger。去。So yeah。

 the point is like。I'm sending a code word， Pre that costs me something。

 It costs me to record L symbols on my C。 That's space on my C， right。

 So the question I have is for those L symbols of space that I'm wasting on my C。

 How many bits B am I getting out of it。😡，I want to get a lot of bits out of that right because I'm you know。

 the more bits I'm getting out of it， the more the less kind of redundancy and the less space wastage in my encoding。

😡，So getting the biggest B as possible， well B is just the logarithm of the cardinality of C。

 so getting B as big as possible means I'm getting the log of C as big as possible。

 which means I'm getting the cardinality of C as big as possible so the name of the game is like if I fix these three parameters QL and D the name of the game is get a QLD code that's as big as possible。

😡，Okay。😊，And。Kind of the rate so you know， people talk about this encoding。

 there's another parameter whichm I'm not going to spend too much time on， but。

There's the problem which is called the rate。Which you can think of as like the efficiency。

Of the encoding。Right， so in this picture， you know， basically what it's saying is。嗯。I went from。

 you know， essentially I went from B bits to log based two of C bits， right？😡。

And the rate is defined to be that ratio， so it's basically B divided by a log base two of C。

And it's always between one and zero。And you know， I want。To be。As close to one。As possible。ai。

 is that right？DidDid I guess guy goof at？That it's in the denominator。 So okay， so the point is。嗯。

Yeah， wait， something it looks a little off here。嗯。

Its sort of log base2 of C should it be oh sorry sorry I know what I give here so what I should have said is the following。

So。So， so let's let's actually just say to make my life a little simpler。

 let's say that I actually wanted to， the message itself is over the same alphabet。Basically， if not。

 you have to introduce a log queue somewhere。😡，So the point is I took a B length vector and encoded as an L length vector。

😡，Right， so I blew up I blew up the length of the vector and the ratio。The ratio is the rate。

Because that make sense， so if I didn't blow it up too much， then the ratio is is close to one。

 if I blew it up a lot， then it starts getting closer to zero。对。嗯。

If if the original alphabet was actually 01， then I guess I would need to。

Put a log queue into this ratio as well。O。So anyway yeah so the name of the game is basically I want to make I want to get as many code words like as I can so let's show that there that there do exist good codes meaning that I can get。

I can get the size of the code to be big。So theorem。嗯。And you， before I write the theory。

 let me also let me write a turn off bound as a reminder。

Because we're going to use the turn up bound to prove this。It says that， let's say。

If x1 up to xn are independent。And they're each in zero1。And let's say x is the sum of the Xs。

And I's say the expectation of x is mu。Then the probability， this is the upper tail for turn off。

 the probability that x。Is bigger than one plus lambda times U。

 So it's bigger it's bigger than its expectation by an extra， you know。

 one plus lambda multiplicative factor is less than e to the lambda over one plus lambda to the one plus lambda。

To the mirror。And I did include a proof of this in the lecture notes at first I didn't and then I thought maybe it'll be beneficial for everyone to do so so I did update the lecture notes and the proof is there in the probability review section。

The thing to keep in mind is that， you know if let's imagine that Lambda is actually very big。😡。

Right so it's much bigger than E so you know the numerator have an e to the lambda。

 the denominator have a one plus lambda to the one plus lambda so if lambda is much much bigger than E。

😡，Then E over one plus lambda you know the one plus lambda does what dominates in the denominator and if if lambda is really big。

 then one plus lambda and lambda are essentially the same right then this becomes something like。😡。

You， just how to think about it lambda to the minus。Omega lambda U。

If lambda is like much bigger than one， let's say。So that's the regime that we're going to care about today。

So theorem。I' would say for any。You know， given integers。Let's say Q。And n bigger than one。

There exists。A code C。Let's start right here。What again。Sorry right。What is begin。

 I'll tell you'll see in a second。There exists at code C， which is a subset of Q to the L。For L。

Equals big O of Q log n。Such that。The size of C is n。And。The distance。Of see。

It is at least one minus。O of1 over Q。I think in the notes I do the calculation a little more carefully。

 I think I got one minus6 over  Q， let's say。So good。So this is giving us something yeah。

 relatively of distance yeah。Sorry， just to clarify is D size of C like the space of all code words。

Yeah， so C is just right， C is just a set。Right。So how big is that set。

 how many code words do I have？听。嗯。Good， so let's prove this。

And it's going to be approved via the probabilistic method。And if you haven't seen such proofs。

 basically the idea of the probabilistic method， and there's a book called the Probabilistic methodthod by Alone and Spencer that has a ton of examples of this。

😡，With varying levels of sophistication， but the basic idea is I'm trying to show that some object exists。

 right， a code exists with certain parameters。😡，How do I show that it exists， Well。

 I defy a distribution。😡，And I draw objects from that distribution。😡。

And I show that the probability that the object I select has that property is strictly bigger than zero。

😡，If it's strictly bigger than zero， that means there is some chance I get the object。

 which means it exists。😡，Okay。Um so I don't let me not do all the details precisely because I do have every last detail of this in the lecture notes。

 but you know the idea is。😡，Is to pick。Basically， C1。C安。Independently。嗯。Each uniformly。At random。

From。Q to the L。Okay。😊，And then what I do is I look at。嗯。The hammering distance。Between， let's say。

 MCciI and CJ。And by the way， this collection here， I'll just define to BC。So let me just write。

 I don't want to because I'm going to use indices for other things too。

 so let me just call them CN and C prime。So here now CNC prime， let's say， are some arbitrary。

Different。Things in。In the code？So take two vectors。

In the code that you know have different indices actually I shouldn't say it like that so okay you know。

 sorry。😊，Let me let me actually you know you don't know your prior already that they're different right because since you chose them independently you might get the same code word twice so what I really should say is that。

You know， C and CJ here in so let's go back let's go back to the indices， sorry about that。

This is a random variable， right？😡，And I can write it as。You know。

 the sum k goes from 1 to L of like yk， where yk is an indicator random variable。

 basically it's equal to one if CK is equal to CJK and0 otherwise。喂。

And then now I can define capital Y to be the sum overall k of y k Oh well， okay。

 I already said so capital so let's call this。Yeah， so let's just call this capital Y。

So what do I expect capital Y to be？Well， this is just L over Q。Right。😊。

Because each YK is one with probability one over  Q and zero otherwise if these things are uniformly at random and independent。

So my question is， you know， what's the probability that？What's the probability that？

Y is actually bigger than its expectation。So I'll say one plus five。Times L or Q。

So here basically this is Lambda。Right。I'm bigger than one plus lambda at times my expectation。

This is that most。5 to the minus omega。You know，5 LQ。Something like that。And the point is now。

 look at how I chose L。Yeah， where I choose L so here I chose L to be basically Q times log n。

That's right here。Some constant times Q log n so the queuees cancel I get。

 you know some basically this is the same thing as like。X of minus omega。You know， Ella Rickke。

 right？And because I chose L to be Q log n。X of minus omega l over  Q。

 I can rig it so that it's much less than， let's say1 over n squared。ok。

So I took a fixed pair and I said the probability that that pair is too close。😡。

Is and has too much overlap right being having large distance is the same thing as saying I don't have much overlap in equal symbols right so saying that I have overlap at most6 L over Q is saying that the distance is at least L minus that it's at least L minus 6 L over Q which means my relative distance is one minus6 over Q which is the thing that I wanted to show。

😡，USo anyway， the probability that two code words are too close is that most one over n squared。😡。

A union bound now over all different pairs of code words。How many pairs are there and choose two？

N choose2 is less than n squared。So by union bound， the probability that there's some pair。

That's too close is strictly less than one。Which means that the probability that no pairs are too close is strictly bigger than zero。

Which means that there is a way you know it's basically you know it's possible you know it's a proof of existence by the probabilistic method right there's some positive probability that these these code words actually satisfy what I wanted。

 which means that the code that I want exists。😡，对。Questions about that？So let's go to the next board。

So let's just remember what we said here， so we said basically Q is fixed。And is fixed。

And I got relative distance。Relative distance D， which was like。

Something like at least one minus six over  Q。And I got block length。Which was O of Q log n。

So corollary。嗯。You know， given。Now， basically。How do I want to write this given Q&L？And N。嗯。

Now I still want to say this。There exists， let's call it a BqL， which is a subset of。0，1 to the n。

Where n is now， let's say Q times L。Such that the following are all true。For all X in B。

The support size of x。Is exactly L。What is the support size of x， support of x is just？

Instead of alli such that X is not equal to zero， so it's like the one entries basically。2。Sorry。

 what is B？That's the crawler is B exists， given Q&L there exists to be。😡。

B is a collection of Nbit vectors， I see thanks。嗯嗯。Where n is  Q times L。

So all the vectors in B have the same support size， they have the same number of one bit， such as L。

😡，I also know that for all x not equal to y。In BQL。嗯。I want to say that。They don't overlap too much。

So。You know， again， bit vectors and sets are kind of the same thing because given a bit vector。

 I can interpret it as a set which just contains all the ones of the bit vector。

 so let me abuse notation and also treat it as a set。😡，X intersect y。So those are the bits。

 those are the one bits they have in common。That's at most。Six hour or Q。And three。

Lastly I want to say that this B is large。😡，The size of B。Is that least X？Of mega。

I thing I want to say El Q。Is this basically just interpreting the code words as like a as basically a matrix like you have？

Yeah yeah， basically I mean so yeah you can well I mean yeah there's no you can do that there's the matrix doesn't really you're not using any matrix operations。

 but you know， yeah yeah， basically there's going be a single one for each of the Q rows or something so basically you just write you write each symbol in unitary the is what you do yeah。

嗯。So right， just as you said， so you have a code word which has， you know。You know， first of all。

 we know that there's a good code by the previous theorem so that good code looks like C1， C2。

CL where each C is a symbol between one and  Q and what we'll do is you know for each one of these。

For each one of these symbols。We'll just blow it up into a bit string of length Q。😡。

Which has a one corresponding to what that thing was and is zero everywhere else。唔仔。And。

So now we've blown up。We've blown up sea。C now has。You know， QL bits。

Because each of the L entries got blown up into a bit vector length Q。So this is my end。

And the support， the number of ones after I do this is exactly L。

Because each entry is giving me one one。And the second item。

 the fact that there isn't too much overlap between distinct code words is exactly， I mean。

 that's basically the same thing as saying that the distance of the code was large。

 meaning that none of the code words overlap too much having equal symbols。Okay。

So we're going to use this corrollary now to finally prove our lower bound。HQ is the。

The alphabet size， then now is the length of the。Yeah。

 so in the original code Q is the alphabet size now now you know for B， Q is just some parameter。

It's some parameter that ends up， you know， it ends up making sure that you don't have too large of overlap between any of the bit vectors。

So you can say look， like I want to have a large I want to have a large collection of bit vector。

 okay， so let's stop talking about bit vectors， maybe it's easier if I talk about sets。

 bit vectors and sets as I said， are the same thing。😡，I want to have a large collection of sets。

Each one is a subset of one to n。😡，Each set should have the same size L。😡，Okay。

 I want to have a large number of sets， so that's item three here。

 number the size of my collection is large。😡，And then item two says none of these two sets should overlap that much。

😡，Right you know in principle， I could take all subsets of size L there and choose L of them。

 the problem is some of those differ by only one element， right？😡。

Um I don't want that I want to make sure that all the sets in my collection are very different from each other。

 no two of them intersect that much。😡，对。So that's what item two is giving me。By the way。

 the reason that you can't make it log base two of Q is for the second one， right？

The reason that I cannot make like like we're wasting space right by by embedding these Q alphabet words into like bit arrays of length  Q like we could if we wanted just to to say their values right we could we could do that and log Q bits right but ultimately we're taking yeah intersection size right or yeah but but you can't do that for two basically right？

For two， for the second part of the corollary would not work if you did that。嗯。That's true。

 it wouldn't。Yeah， that's true。Okay， so let's finally let's this like finally now actually prove our lower bend let's let's get out of codes and go back to lower bounds so let me let's remind ourselves right in the corner of what we just said we have so we have that BqL。

😊，Is a subset of。0ero，1。So the n or n is QL。嗯。诶 know个咩？Let me just keep thinking of it as sets。

 I think that'll make our lives a little bit easier is a subset of like the power set。Of one to n。

 so it's like the power set of one n is the collection of all subsets of one to n。

I know that for all sets， know lets say。For all sets。Q in that collection。MeQL。

 I know that the size of Q is exactly L。I know that。

What else do I know I know that for all Q not equal to Q prime in that collection。

 if I look at Q intersect Q prime that's at most6 L over  Q and I also know the finally that the set is big so。

The size of EQL。Is at least exponential omega。E Q。Okay， so that's that's what I said right now。

So theorem。Suppose script A。Provides。A 1。1 approximation。To the number of distinct elements。

More precisely what I mean is it outputs a T tilde such that T tilde is at least。

TL does at least T and it's at most 1。1 times T。And is deterministic。Using。Es bits a space。

Then S is omega n。So let's prove this。We will show that the of the existence of such an A will show that implies the existence of an injection from a big set to a small set will show that there exists in injection。

Encoding which maps。嗯。Basically BQL。嗯。Into。basicallys。Zero1 to the S。For。嗯。Q is equal to 100。

And L is equal to。嗯。And over Q。Because remember， l times q is equal to n。对。So。

How does this thing work？嗯。I should say there exists and this thing is an injection， of course。对。

So the encoding is as before。Meaning， you know， we have this set that we'd like to apply the injection to。

 we take all elements from the set and we run our streaming algorithm over it。😡，Okay。😊。

Then we take the memory content of the algorithm is then is then the encoding。

 so the question is the decoder， how do you do a decoder？去。

So this is going to be a very inefficient decoder。😡。

But it will successfully decode proving that our encoding is actually an injection。

So I'll do the following。For x in or I said now， so now it's actually a sets， right， so for Q。In BQL。

First of what I'll do is a dot in。So here's what I'm trying to do I'm basically you know I know that some elements of BqL was encoded。

 I just don't know which one。😡，So what I'm going to do is I'm going to loop over all of them and I'm going to test。

 is it this one or not。😡，Okay， and I'll show you that I can test it。So okay。

 so I'll initialize so every time I go through the for loop。

 I really initialize a to the memory contents of M。 So the only thing that a has seen so far。😡。

 the let's say' I'm trying to recover。I want to recover， let's say some。You know。

I'm very bad at coming up with letters。F。Such that。M is just the encoding of F rate。

So the question is， is Q equal to F or not？So every time I go through the loop。

I reset the memory contents of A。😡，To be what it was right after the encoder ran a。

 which means that the only thing a has seen so far is F。系い。So now is Q F or not。

 so then what I do is。For I in Q。A。 updatedate i。Right。So now。Now after the for loop is over。

 what is， you know， what has a C， you know， basically this is a comment now a has seen。😡，嗯。F Union Q。

Right。Sorry， I did not I did not mean to make that look like a swear word， okay。

 so that was poor planning on my part。So。So the point is if  Q were actually F。😡。

Then F union  Q is just f again， right so there are two cases either Q was F or it isn't if F union  Q is equal to F。

😡，Then what's the number of distinct elements？😡，It's L， right。

 because all the sets have exactly the same size L。😡，Which means that when we query the algorithm。

It's going to output a number that's at most 1。1 L。😡，喂。Otherwise。If Q is not equal to F。

Then almost all the elements in Q are new because F and Q don't have a lot of overlap。

Which means that。Basically， F union and Q has size almost 2L。😡，Right。

 which means that the output of our algorithm is going to be very large。

 It's going to be much larger than 1。1 L。So we say is， you know。If。A dot query。Is at most 1。1 L？

That just returned。Q。Otherwise。We know that F Union Q has size。Equal to。

The size of F plus the size of Q minus the size of the intersection。This is L。This is L。And this。Is。

At most。I said that Q was u did I pick Q I said Q was 100， I mean that was being very conservative。

 but I know that this is at most 6 L over 100。Which is like 0。04 L。In other words。

 this thing here is going to be at least 1。94 L。Right。

 so it's either going to say an answer that's less than 1。

1 l or it's going to say an answer that's bigger than 1。94 l so you know that's it questions about3。

06l。06 L instead of 。04 L， if it's 6 over or 100。嗯。Wait， so on the right hand。

 the right hand bottom right， is that6 over 100 L equals 。04 L point Oh yeah yeah。

 I'm really bad at math This was point。94。96。 Yeah， yeah， right。😊，Yeah， okay， any questions？Okay。

 and you can ask the question I mean。You can tell here that kind of by the way this argument works。

 you'll never be able to show a lower bound like let's let's suppose that instead of 1。

1 suppose that I put here。😡，You know，50。Right。Um， you'll never be able to prove a lower bound via this technique because kind of the limit of this is approximation factor of two。

You'll never be able to prove a lower bound for an approximation factor that's bigger than two。嗯。😊。

Although it's known that you if you are looking specifically at alpha approximation。

 let's say you're looking at。T tilde is less than it go to alpha t is at least t。

There is an omega n over alpha bit lower bound。It's just not this argument。

 it's an even more sophisticated argument and I do have a reference to it already in the notes so you can take a look if you'd like by Chkabarthy and I forgot the second author's name starts with an S。

 but you'll find it in the notes。Okay good， so deterministic exact is impossible in sublinear memory。

And of course， you know， what's what's so I maybe I should have written it explicitly。

 I didn't write it explicitly， but what's the actual lower bound you get。

 the actual lower bound you get。Here， you know， there exists this injection that implies that S has to be at least。

嗯。Omega log or not even just omega， but。It has to be at least。The logarithm of the size of BQL。Which。

 you know， by the guarantee that I wrote up here。Is at least Oomega n。看。So let's do one more。

I don't know if we're going have a chance to do the quantiles one I mean it's it's a very similar argument it's based on codes it's based on this compression idea it's just of course it has it has to be a little different because now the you know the queries that your algorithm supports are not distinct elements queries they' quantile queries so you sort have to show that。

Being able to answer quantile queries can still let you get enough information to decode。

So I you know， given that we only have 11 minutes left I probably won't have a chance to do all the details of that。

 maybe I'll just leave that as you can investigate in the notes if you're interested。

 but I do want to show you now the randomized distinct elements， you know。D。

 I have a quick question for an epsilon approximation。

 what is the dependence on Epsilon and the lower bound？That's a good question。

 so here kind of as long as you're getting some approximation that's。😊。

Like strictly better than two you'll get a linear lower bound and it's not you know。

 what what you what you'd imagine is if I want one plus1。

000001 approximation that should be harder because you know I'm asking I'm demanding you know。

 an even better quality of approximation， unfortunately。😡。

This particular argument is not sensitive to sending epsilon to zero。

'll just you'll still get an omega and lower bound。😡。

Where the constant doesn't really depend on Epsilon or maybe maybe like， you know。

 the constant might converge to some fixed constant as Epson goes to zero。

 but you're not going to get。You're not going to get anything really that great the truth is you know for randomized approximate algorithms。

There is a lower bound of I'm writing this in the corner， top top right。

There is a lower bound of omega1 of Repson squared log n。Okay。

 this lower bound is via a communication complexity argument。

 remember I mentioned there are these two kind of classes of arguments compression and communication complexity。

😊，So。Oh， sorry， not times， but plus。Yeah， so one of our squared plus login bits is the both the upper bound and the lower bound。

 there's a matching algorithm that achieves this。嗯。😊，And you know。

 the log n part comes from a communication problem called the just equality testing， which。

you'll see later in the course and onerup on squared comes from a reduction from a communication problem called gaphamming again that's something that you haven't seen yet I don't expect you to know what I'm talking about。

 but are these are via different arguments those arguments don't look like what I'm showing you today。

Okay。The problem。So。Suppose now。CryptA is a randomized。Exact algorithm。Succeeding。

With probability at least two/3。Using S bits。A memory。Then S is again， omega n。Okay， so。This is also。

I would say no more complicated than or maybe even less complicated than the deterministic approximate algorithm lower bound。

But it does require you to reason about things in a way that you might not have done before。

 so you it'll be beneficial to see this， maybe expand your mind。So the first thing is I can you know。

A exists。Implies。A prime exists。With。Failure probability， let's say at most10 to the minus6 using。

Oh that expensive memory。Why is that？Just to apply the algorithm a bunch of times Yeah。

 so this is something we saw before when we talked about Morris plus and Morris plus plus and Fm plus FM plus plus this is basically the plus plus idea。

 right？So a prime will just run。A lot， you know。100 copies of a in parallel。

 100 is too much you don't even need that much， but it'll run 100 copies of a in parallel。

And then at query time。It'll query all the copies， it'll get 100 different answers。

 and it's going to output the median。😡，And you know。

 that will work as long as at least half the copies worked。

 which happens with really high probability by the turnoff bound。So。Good， so basically， you know。

 we can get this basically for free so from now on。I'll just assume。A fails。

 itself fails with probability at most 10 minus6。Will'll show that。Their exist injection。Ink。

Which maps B into01 to the S。Where。B is going to be a subset of BQL。

And the size of B will be at least half the size of BQL。So that implies that。

That implies that S is at least。Log the size of B。Which is at least。Log。The size of BQL over。嗯。Two。

 which is omega n。And I'm going to again do this with Q being 100 and L being like n over Q。Again。

 that's conservative， that's not necessary。Okay， so how did the encoding and decoding work？So。😊。

I'll call it encoding prime。Definitely the same as the encoding from before。

Why can't I just let this be my injection？What is an injection， it's a function， right？Ik， you know。

 yeah， it's random Like this is a random function。 I mean， it's its behavior is random because it's。

 it's using a and A's behavior is random。 So this is not a fixed function that's behaving in。

 you know， some fixed way。 Well'll fix that。So for right now we have this randomizingcoding。

 we will eventually， you know， by the way， I mean， that's why you' this is a little foreshadowing。

 I mean that's why。I had to deal with I had to do this。

Right that's why other why don't I just have my injection B from the entire BQL。

 it's because well yes innc Prime will end up working on the entire BQL。

 but I need to somehow extract the deterministic function and I will be able to do it for a very large subset of BQL。

And。Deck prime。Will be the same。As。For deterministic exact。Lurbound。So that was the one just let's。

I think that was。Here。Right。So what I do is， you know， I try to learn， I try to learn the bits。

As one by one。Through this for loop， so I'm going to use the older version of the decoder and again it's randomized because it's using a and a is random。

😡，Now。What can I say？The expected number， this is over the randomness of a。

 the expected number of errors。From decoding。B linear of expectation。

 right each bit that I try to decode。Remember， now this is again， I'm viewing again。

 these sets F andq as being subsets of one to N。So I'm trying to learn end bits here， right？

So each one of these bits I'm learning。😡，I， you know。

 I fail with some probability 10 to the minus six。So the expected number of errors is at most 10 to the minus6 times n。

Right。Which means that the probability。That。Let's call it， you know。

The the decoding prime of the encoding prime。Of some fixed set。呃。The probability this is wrong。

We're actually。Okay， so。Okay good， so let me go back here。The expected number of errors is that。

 which implies the probability that the number of errors。I's bigger than2 times 10 to the minus6 n。

Is less than a half， this is by Markov。Right， and if I have less than two times 10 to the 6 errors。

 I can， you know， I can decode the aircrafting code that basically uniquely determines。

Which element of BQL I have？😡，So I'm saying that this is true。

 the problem that the decoding of the encoding of F is not equal to F is less than a half。

It was's the probability over the probability is over some random string R right so you know a whenever you have a randomized algorithm a that's operating some input X。

 this is kind of the same thing as like a deterministic algorithm operating over x comma R so this one is deterministic this a is random。

😡，And kind of this， this R here is basically like my random string， it's the source of my randomness。

Right。A randomized algorithm is simply a deterministic algorithm that has two inputs。

 one being the actual input and the other being the random string。Okay。

So now what I can do is I can define indicator random variables。😊，Let's define。Zf。Is one。If。嗯。

Z1 is1 if。The decoding prime of the encoding prime of F is equal to F and zero otherwise。

 and what I know now is the expectation over R of the sum over F in BQL。Of Z F。

Is bigger than BQL over two。By linearity of expectation， right。

 each Zf has expectation more than a half。So the expectation of the sum is bigger than BQL over two。

 which means that。There exists in R。A fixed car。Such that。If。If I run。Innck prime D neck prime。

Withs let's call this R star， it's a fixed string。With R star as the random string。It's not random。

 but it's fixed。For a。You know， it works。For。At least。BQL or2。Sets。And let me just call these。

That's my B。So that implies that you know， I have an injection now from that B。In two01 to the S。

The injection is run the encoding prime algorithm with the random string being our star。😡。

And similarly， the decoding is run the decoding algorithm with the random streaming our star。

So questions about that。How did you get the bound？It's greater than half on the baby's page。

You're talking about this thing like you used moreovs。

 but how did you connect that to the decoding of the encoding？Oh yeah。

 so I guess I swept that on I mean， how did I go from here？To here， yeah。

I guess I should say one thing， which is。I do have to change one line。

I do have to change one line here。In the decoder， I'm not actually going to return X。

 but I'm going to return what I'll call like。Ar correcting code decode of X。If that makes sense。

Right so like yeah it's the same it's the same kind of argument I had with these with these with these balls。

 so the point is I have I have this collection BqL of like sets of size L。😡。

And they're all they're all pretty far apart from each other， right？Yeah。

 so if I take one of them and I corrupt it by like deleting a couple elements and adding a couple elements。

 I can still uniquely recover what the original set was。

Right so that's basically all I'm doing over there， I'm saying。You know。

I know that my expected number of errors introduced into F is at most n over a million by deck prime。

 so the probability that the number of errors is more than two over a million times n is less than a half。

 and if it's less than two over a million times n， that's a small enough number of errors that it uniquely identifies the element of BQL。

嗯。Which means that my decoding will succeed。Yeah， good question。 I didn't say that explicitly。

 And so does the million not depend on。Yeah。Yeah， it has to do with。嗯。

Oh like the intersection yeah like basically you like you don't want to get swamped right you know that these elements have。

Each one of these coFs has L elements in it， L is what n over  Q Q is 100。

So I have these sets that have sized n over 100。Yeah。

 they have very small intersection with each other。 Their intersection sizes are 6 L over Q。

 So that's basically6 n over Q squared。So that's you know， six and over 10，000。

 so they have very small intersections。And then I corrupted one of them by adding two over a million times n extra elements in it。

 possibly deleting and or inserting two n over a million elements。

And I want to argue that that still basically uniquely determines what my original F was。Yeah。

Yeah good question， maybe I should have said that a little。Slower。Any other questions？And yeah。

 I did not get a chance to do quant， let me end in the chat， I see。Okay， good。

the ultimate algorithm depends on this like our star。Yeah， so our star will be kind of the。

 it's there to remove the randomness。So that I actually have like an， you know。

 honest to goodness function as opposed to some randomized procedure。Oh okay。

 the decoding and encoding works on like over half of them。😊，Well。

 the popularity that it works is over half so those。Right， so yeah， so for any fixed F。

For any fixed stuff。I can define this random variable here。And that random variable。

Is one with probability more than a half， that was what I got out of Markov。

 so it's zero with probability less than a half。Which mean when Zf is 1。

 it means I succeeded in recovering F， right？So for any fixed F。

 this scheme works with probability more than a half。

And then I use that linear rate expectation to argue that。嗯。

In expectation over the random choice of R， I will work that that R in expectation works for more than half the sets。

😡，So by averaging， there must exist in R that works for more than half the cents。

Not everyone can do worse than the average， right someone has to achieve at least the average。Okay。

So good， that's all I have for you today and I will see people you all on Wednesday。



![](img/150909d6661a64660cb147ea96288e02_2.png)