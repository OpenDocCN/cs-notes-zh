# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p32 -32-  L26_ Problem Solving I (Spring 2025).zh_en -BV1iV1XBWEJW_p32-

![](img/7176960e250c3a77834f7c411cd3255e_0.png)

Alright， yeah， we'll solve the fourth question from the exam。

 So the fourth question is about the FSMs， the finance state machines。 So in this question。

 you are basically given a state representation of， of FSM。

 And the question ask like several questions related to the FSM， for example。

 the representing it in a boolean equation in in， in one head encoding。

 binary encoding and out encoding。 And as well as like what's wrong with this representation。

 And we're gonna try to correct it。说。You can see it right， okay。So for the first。

 so for the question， we have states and for the states， we also have the output。

 and these are the Ts and TBs are inputs。 So the question ask。

 so there is a critical component missing in the FSM。 And what is this missing component。

 So if you look closely to that FSM， you'll see that there is no reset line。 right。

 So we need to have that in order to have。Basically have a deterministic behavior in that F SM。

 So we'll say that we don't have the。Re reset line。For this affair time。So for the second question。

It says of the two FSM types， which are more than me。 What type of an FSM is this， Basically。

 if you look at that representation， you'll see that the output， it only depends on the。

 only depends on the state， but doesn't depend on the input， right。

 So this means that this is more the representation。So if the output only depends on the state。

 then this means that this is mores。So alright， so far， so good。 I guess these are the。

Relatively the easier ones。All right。So for the， for the C。

 it says that least one major advantage of each type of state encoding below for one h encoding。

 our aim is to reduce the next logic wires， right？ So for the， for the one h。

 we we basically try to represent each next state logic hopefully ideal a bit single bit。

 So this means that you reduce。So you reduce next state logic。With the one of how en coding。

So for the binary encoding， our aim is to use the least amount of be to represent the states。

I'm question about the reset signal because the book especially stays。For， for the fourth one。

 for this one。So。So。I'm， I'm actually not sure about this， but like。So does。

 does it say the same thing in the slice as well or， or know。Oally， a recent。

So should we comply with that one if the book says this is optional to have their set line。呃。

Do you think like this is a missing component？As well， like a critical component。

So if the book says this is optional， I will say， yeah， then。Okay， I think for that one， yeah。

 we can comply with the book。 But Kira has a point， I guess。每月。三个。Yeah。Yeah， that's， that's true。

Yeah， thanks for that。がの。第一。I true but I think your book test。The recent that not。

But you need an initial thing。都会一定点心。Yes， with the reset line， we basically define the initial state。

 yeah。一次男。Yes， this is true。こはす。You just have an initial statement on9。哦。I， I will top so actually。

 So you need to you。 So for the representation， yeah， you can say that， yeah。

 this is our initial state。 but to really have it as an initial state Then you should make sure that when you。

 when you start this FSM。It's really gonna be the initial state， right。

 So how do you ensure that you need to have some sort of resett line so that it goes there when you reset and then you start it as an initial state for that。

basically， it means the same thing to have the initial state under set line。ok。

Any questions related to those okay。呃。So for the binaryco yeah， as I said， we。

 we try to basically use the least amount of piece to represent the state。

 So this means that you reduce the Philip flos that you need to represent the states。 So this is。

 I would say， the major advantage of binarycoding。Reduce ph flos。And for the output encoding。

 our goal is to basically use the least amount of logic units for， for， to encode the output， right。

 So this is also clear。I guess if there is no question with those。Okay。So starting from the。

 the question ask us like， so， okay， we are given those states。And like。

 so how should we write the basically the pollan equation of that of that state。 And we have。

 and we have three options。 One option is one hang one head to encoding and second option binary as we can see。

 And then the third option is up to encoding。 So for all of those。

 the what changes is basically the way that we represent the states。 and the rest won't change。

 right？ So， and basically so what I'm gonna do now is。I'm gonna write a through table。

Kind of like a higher level to table。 I would say， because I'm not gonna represent the states with the with the bits。

And this will be my kind of like reference for the next three questions， so。For that tool table。

 I have current state， let's say。I have my。TA。TB。The output is too big， So all one。

All0 and the next state， right。So for the current state， starting from the A， let's say。

 So if I have， so the T A basically don't care。 So if I have T1， I'll go to opposite visit C。

For again being in Sta C， A T A， don't care。 And if I have T B not， I'm sorry， yeah。That's。

So if I have0 here。So I'll visit P。 So if I have one here。

 I'll visit C and the output when I'm in in state A will be 10，10。 So for the state B。So， if I have。

04 T A，4 T A， then always it C。 Then this means that0 and don't care for T B。See， right you see。嗯。

So for A and B， if I have T A 1。Don't care for TB， then I'll visit A。And the output will be one once。

For C。So no matter what I'll visit D and these T As and T Bs are don't cares， and the output will be。

The 0，1， and the next state will be D。4D。So if I have04 T B and don't care for T A。

Then this means that always it be。And。If I have one for when， when I'm in D。

 then this means that I'll visit D again， and the output will be。00按0 zero。

So let me see if everything looks good here。😔，T 0， I guess yeah will go to be。And TV1 will go to see。

 right。 Okay， so the， this tool table is basically like a kind of like a higher level tool table here。

 I will say because I don't have the bits for the current state and the next state。

 But I have the explicit bits for the output and and the input bits， basically。

 So for the following ti questions， basically， what I'm going to change。Are only the current state。

 the way that I represent the current state and also the way I represent the next state but。

Those will not change， right。 So these are basically independent from the。

 from the encoding that I'm using。So I'm going to use this as a reference for the following questions。

 So I already written this basically， if you wonder。To save some time。For the one encoding。

 So what I'm gonna do， I'm gonna try to represent each state using a single bit。

 Then this means that I'm， I'm gonna write it like that。 So， for example。

I can represent a with the least， least significant beat。And be as follows， see。Andy。Rightright。

 so here then this means that every state is represented by a single bit。 So I'm gonna。

Put that into the table that I've written here。So I'm gonna represent the current state as C 3， C 2。

 C 1， C 0。 and the next states as and 3 and 2。And1 and 0。 And basically， so if you remember。

So those are， those two rows are A A。 So I'm gonna write the way that I represent a here。

 and which is。This。And the next state was B。 And I present B as follows。And again。A。

 because I have a here。 And next state for the， for this one will be C。And yeah。

 I think you kind of got the rest。So this will be B， and the next state will be C and。

The way I represent C like this。And。AB。And the output will be a。So， this means that this。So。

 I have sea。And I'll put the next will be D。And for the。I have first B here。And again。

I have the here。Alright， so this is a tool table for， for the。Which one， I'm sorry。的。Let me see。yeah。

 yeah， yeah。 you're right。 So this， this will be 0， right。Yeah。And this will be。1， I guess。Yes。

 that's true。1 TV is0， yeah。I go to V and And TV1。 I go to C。 That's true。 That's correct。Okay。

 so based on that， basically Iright， the the， the， the next states and also the outputs， I guess。

 right。Yeah。C and v okay。嗯。Alright， so let's write and3 here。So I'll check like when entry is one。

 entry is one when for the， for these two rows。And for the one hot encoding basically。

 this means that we should， we ensure that if one one of the bits in the input is one。

 then this means that the rest should be 0。 so we can regard them as don't cares so。When the。

 when the entry is1， this means that C 2 is one and。And that's it， I guess。

 So let me do some s check here。Yeah。Alright， so， and the second one is this When N 3 is1 and C 3。诶。

And also， T， I guess。Alright， okay。So， for。For n2， I have two rows as follows。

 So when n2 is one here， I have c 0。1， and also saw TV as one。Right， yeah， that's， that's correct。

 And again for N， and2 is one， C 1 is  one。And also， T A is 0。So， T A not。Let me check it again see。

 okay。So， for。4 n1。So I have here and1，1。 So this means that c 0 is1。And so， I have TV。As 0。Okay。

And for that one， I have C 3。As one， and also。And also， we have TV 0。

So this should be simplified as if I'm correct。TV。C，0 or C 3， right。Okay。Yeah， for the next。N 0。

 I have。I have one here。😔，And that's it， I guess。 Yeah， So this means that C 1，1。And also， T， A 1。

Right。Yes， okay。So these are the next state logic the equations for the next states。

And for the output， for output 1， I have one。When， basically。So I had the output form I basically。

Either C，0 is one。And it doesn't。 It also doesn't depend on the T A or T B or when C1 is one， right。

Can you see that。The rest。 So O1 is one when either C 0 is1 or C 1 is one， right。

 And for the Z C 0 row， then I have the T A already they don't care。

 And T B also doesn't change the result。 And it's the same as well for the for the T A。

 So I I only have C 0 and C 1。For00。All0， I have one here， so。I have C1。1。

 and it also doesn't depend on the T， A， or I have C C 2，1。And I guess that's， yeah。

 that also doesn't depend on the input。 Yeah。 So these are my the。TheB equation for。嗯。All right。

 so the。We， well move on to the。有么。So for the binary， so basically， we can use two bits for。

 to represent four four states， right， So basically， I'm gonna represent a then at 0，0。

 but it's all up to you。 how you represent。 It doesn't really matter。But like。

 make sure that you use like minimum amount of peace to present the state。

 So the same thing that I've done like in the， in the previous question。 So， but this time we have。

Only2 bits。 And this means that。Allright， That follows。 So 0，0。 And let me follow that one。嗯。 yeah。

 follow that phone。Again。0，0， I have0，1，0，0。 I have 10。0 one。I have a 1，0。0，1。 I have0，0。41，0。

 I have1，1。For one，1。I have 0，1， and againm for 1，1。 I have 1，1。

 So this will be the true table for to represent states in in a binary encoing and。So， yeah。

 let's try the。嗯。Let's right， next。Sa logic unit for n0。 I'm gonna write tears。For n0。

 I have one here。For here。 So this means that C 1 n C，0， n and T B。Is one， okay。Or I have one here。

So notice that I， I always have C1 S1 and。1 c 0 is 0。 I also like。

 I don't also depend on the T A T B or1 c，0，1。So it also doesn't depend on the either T A or T B。

Okay， I guess that's the。That's the answer for that one。 Let me check。Yeah。呃。Yeah， and。She。😔，Yeah。

 then yeah。 we can also simplify that， right， So this is always one。For anyone one。

 I'll check the row。 I have one here。 So this means that。For this one， I have C1 not and。C。

0 nots TV not。哦。S not TV not all。c咯。😔，呃，TA。Okay， and for these ones or。I have C1 as one。And c 0。

 not or here。C，0 and T。I guess。 so this should。诶。Yeah， this is， as is， yeah， this is not simplified。

For all one。So I have one here。 So this means that。C1 is always0。呃。For that one， if I have c 0。Not。

 this also doesn't depend on the。Yeah。I guess only see one here。 Yeah， only see one。

 but that's right。see，0 not or。でしろ。And for。For all0。 So I have one here again。And。C1 will be。

C 1 will be 04 two rows。And。Also， C will be， let me write it。In this way。And yeah， I have。

 I actually have。C 0， not and C 1 here， or。呃希1。C0 not。Right， so you can ignore that part。

So this is basically ex right， so you can write tests。C，0， x Z C，1， S1。RightYeah。

 the question is a bit。诶。Long， let's say， to write。呃 what。Do you have any questions so far。

How I wrote， how I write these two tables， yeah。Like if they don't do it。Yeah so。It's， so it's gonna。

 so it matters for the， for the last question because it's。

 it's gonna restrict you saying that you only have and and， I guess or gates， right？

 So this means that you cannot use the Xor。 basically， you'll need to use the and and or gates。

 But in this question， I guess yeah， you can。诶。Yeah。

 you can leave it as is because using minimum possible number of bits to represent the state。

 So yeah， I guess you can leave it as in， in that manner。Yes， that's true， yeah。Yeah。

But make sure that you also simplify it as much as possible。Okay， so for the last one。

 that will be also， yeah， that's tricky。Because。It ask for the output encoding。

 And this means that I need to make sure that the output is encodeding。

 encoded so that the output logic circuitry will be basically minimized， right。

 So how can I ensure beforehand without writing the without writing the through table and the circuitry。

 So。I'll show you basically how I did it in this question。 So I have two bit。Output rights。

 outputs and the inputs for the states I can use。Let's say，2 bits athletes， at least so。

What I wna ensure is， basically。I want to ensure that when oven one is one。When or1 is one。

 then or one is。Determined exactly， hopefully， by one bit。 Okay。

 so let's say that I'll use two bits for the， for the states。 And this means that C 1 and C 0。

 So let's ensure that， for example， the output 1 is only determined by C 1。Okay。

 and the output 0 is only determined by by c 0。 So how can I then write the encoding in a correct manner so that I'll make sure that the output 1 only determined by C 1 and the output 0 only determined by the C0。

 So you can write it as follows。 So for C 1。So what I want to do is basically I want to have the same bit。

Right， when all one is one， then the first four rows。Then I don't want to have the same bit。

 which is K for the remaining growth when the O one is 0。 So this means that I will have。Ms here。

 So I'm not writing one or 0， but I'm writing K and Ms for the C 0。 And I want to make sure that the。

The， these three roles are determined by the。By the， by a single bit， by a unique bit。

 And this means that let's use why here。For these three。

 and for the rest I that I don't wanna use the same thing。So this means that I will have Z thats。

 So here， what it says that K is not equal to M and。And。W is it doesn't equal to the Z right。 So。

 but what you can see here as well。 So so。So basically， if you give K， for example， one。

Then this means that M will be 0， right。And。In that case， so let me also。Put that up into。 Yeah。

 when。 So， for example， when this is。When you give Z10， then this means that y will be1。Okay。

 so you can， you can play with it as as you want。 But so when you use， for example， these bits here。

 then you'll have your representation for AB， C D。Right， so you can play with those。 You can。

 you can select K0， and then the rest will be assured accordingly， basically。Did you。Get that idea。

 or。Okay。Allright， then let's present a as。 then this means that a is。1，0。Bay as。K1。And Y1。See means。

So I have am here。0， right，0，1 And D here。 I have M 0，0， okay。So， let's try。Then okay。

 let's write it in that sense。So， I have。Ill here then。C，1，6，0， M1， and 0。呃。This is 1，0。

 This goes to。B， then this means that this is。1，1， I have disclose to see this means that 0，1。

one one。This goes to C again C is 0，1。B is 1，1 again， and it goes to a， which is 1，0。I have C here 0。

1， and this goes to D， which is 0，0。And for D goes to B， which is 1，1。 And again， for d。

 that goes to d 0，0。 right。 So yeah， that's a bit long。 So if you allow me to save some time。

 I'm gonna directly。Right。The balloonoleing equation， because what you do is basically。

 I'm gonna again check the one， the rows that are one here and the rows that are one for n0。

 And then I'm just gonna write。As I saw this， this will be C 1， C，0， not and T B。Not。C，1， C，0， T A。

 I guess。And see one not。是。See。C you not。And TV。 And this will be simplified as。C。😔，TV notes。Oh。C，1。

 C，0， T， A and 4。And0， Ill， I will have C 1。C，0， not ears。Or c，0。T A note。or C one。C。

0 not and TV note。And for all1， I already ensure that this is determined by c1 and all0。

 this is determined by c 0 okay。So， this is the。F1。The last question ask。Right。

 so the the last question says that so which one would you choose to minimize the total array of this FSM。

 So if you count' the number of logics in the building equation that I write。

 So you you'll see that we have 10 logic units for one1 hot encoding。

 and I have two bits to represent the Philip to represent states。 and for binary， I have 11 plus ex。

 this would make 14 and two Philips and for output encoding。

 I have again 10 logic units and two Philips。 So in in that manner。

 So using output encoding make sense over the others。Okay。Is there any question。All right。

I guess we can mo to next。

![](img/7176960e250c3a77834f7c411cd3255e_2.png)

Yeah， this question has。

![](img/7176960e250c3a77834f7c411cd3255e_4.png)

Two parts。In the first part， it's warm mapap computing a Fibonacci number。

 so this is about writing MEPS code to compute the Fibonacci number and as you know this is the expression for the calculating Fibonacci number and here you have a high level language code。

 C code。To calculate this fibonacci number， so as you can see we have three variables。

 we have a originally is equals0 b is equal1 and this is C that a is equal a plus B and then we get into this while loop that will be repeated like n minus1 times。

And in the loop body， what we have is we first compute a plus V and start the result in C and then we。

St B in A and C in B。Finally， we decrement this counter n and we repeat the loop while n is greater than one。

So here there are some assumptions， conventions to write or code。

But let's say that the most important thing for now is that。

The argument n that is this counter here is going to install store in register4。

And the result C this C here is going to be stored in register 2。

Then there are also some register numbers for example， for call say temporary registers。

 we' are going to need these because as you will see in the code that this Fibonacci computation is going to be in one function。

 then we have the stack pointer， we're going to need the stack pointer as you might remember to save the temporary registers and we also need one return address because as you remember every time that we call a subroutine we call a function。

 we need to start the return address somewhere and the return address is the return program counter and this is typically starting in Reg 31。

So let's take a look at this code。Yeah， let me do something。So that you can see the code。

So the very first thing that you。You find in this function in this fi actually function is that。

 well， this is the beginning of the function。 and the very first thing。

Is storing the registers into the stack because some of these registers might have some values that are for the main are useful for the main function but these registers might be needed by the function itself。

 you know that the number of registers in every computer but especially in the MIPS computer that we have studied here in this course。

 it's quite limited so it might being necessary to to use some of these registers that are already being used by the main function。

 the the color function so that's why the first thing that we have to do is save in the registers in this case registers 16。

17 and 18。17 and 18， we stored them in some part of the memory that is pointed by the stack pointer。

And right after that， we initialize。The registers with some values because we are going to use them。

Okay。有啥问关兴。Excuse me， You had one question。嗯。Yeah， just to。So it's not。好，突然在这边。哦， okay。

Then you can ask maybe later in the break。Okay， so observe that， well， let's say that this is the。😊。

Function call。 So is this is the beginning of the function right after starting with the function。

 we have to store some temporary values in this stack。 And right after that。

 the first thing that we do is this first。C equal a plus B。

 So this is an addition we store C in register 2 in register 6， 17 and 18， we have A and B。

 So this corresponds to this first C equal a plus B。

And now the next thing that we are going to find is this while loop， right， so in the while loop。

The first thing we do is。Checking the boundary condition。

 So here this is n must be greater than n than one to get into the loop body。

 and this is what we are doing with this set on less than。Immediate。嗯。

We compare this register 16 that contains n。 We compare it to2。And。If。Register 16。Is less than。2。

Then。Register 3 will be equal1。Right。😊，O that。If it's equal one， it won't。Branch， right。

 So it will go。 So， sorry， if this is equal one。It's not equal to0 so if it's not equal to0 won't take this branch so it will go to the loop body and what do we have in the loop body well the first thing that we have is again add to 1718 that is C equal a plus B corresponding to this instruction here。

Then we store B in A。So that's why。What what here we are essentially do is adding。

B plus0 and storing it in a in register 17， we do the same to store C in B。

 and after that we decrement minus1， this is immediate addition minus1 to decrement n right after that we have this unconditional branch。

This jump instruction。To start again and evaluate again， the value。

Of the content of register 16 that contains n。 So we repeat this as many times as needed。Wing。诶。

When 16。is。16 contains n。When 16。Es。Lower than2 then。

This will be0 and then here we will take the branch and we will until this down here and we will finish the loop and the very last part that you can find here in the in the code is。

This restore because remember that in the beginning what we did was storing the content of these temporary registers in the stack now right before leaving the function we have to restore the contents of the registers。

Do you have any questions here？喂。就是已经好的那。Yes。So in the exam。

 what I recommend you to use is to do the notation that。The question itself it's using right。

 so in this case。We are using the numbers， in other case you will use the error or something。

 but as you know and actually you can check in the slides， they have the same meaning。

Yeah are we the return stress？😊，这事是我满意的我。s notYeah， exactly its not it's not overri。

 This is just a convention in D so you can save it in case。In case you might need to use this。

 but this is just a convention， it would not be wrong if you don't overwrideite it， okay？

I told my question before was about the name of the registers。

 but the way we're using is basically bench。Any important。Well， I mean。

Usually if you have in the final exam some question similar question like this。

 we will probably give you this kind of convention if we don't give it to you。

 you are not required to know exactly this， but you can check in the slides and you will see what are the typical registers that are used for some particular purpose。

ok。So thereは。The register one the officer。啊是。Just感问。It's just a convention， exactly， I mean。

 if one question like this asks you to stick with some convention。You should state。

 it's not more than that。I don't understand， why。The richest person。W is6。F3 doesn't mean that。Can。

So very important。我位于。关于。好的。喂。So they are callli saved because they are saved by the callli right this doesn't mean that the color cannot use them before calling the function before calling this Fibonac function we have some other function maybe a main function that calls the Fibonac function and this main function might be used in this registers if we have this convention and every time that the function is called we store these registers in the stack we are on the safe side。

Right。Yes exactly it might I mean this keep in mind also that you write this fi actually function just once right and then you might need to call it from different place in your main program or in different programs and sometimes you might be using these registers sometimes not okay。

Yeah。So。Because in this case， in order variables。teachers有。Ca谁。有你。And to say。

The those is on the stack because they've called their safe。So being the call can。I mean。

 your question is related to his question。In some particular situation， you might be able to do that。

 but the thing is that you are going to write this function just once。

 you just want to write this function once and you know that in this function there are three registers that are used that are 1617 and 18 and you're going to operate using them it might。

Happened that sometimes you are really using these registers other times not， but it is。

Save to have this convention that those registers that are going to be used by the function are by default。

 save in this stack and this way you avoid any possible overri prevents a case。月11号。

Co state and state。Saing。Ivent they didn the exercise and produce it。还。Yeah， sure， but。

How do you know that these have not been are not in use by。Per prevention。

 they should be called their。他告出是。Yeah， okay， you have another question Yeah。

 during the semester we saw weekss as well as。We have to like。Know the book really well。

 Or is it like more。Well， I think that you should know really well what Professor Mulu has explained in the lectures and you and ideally also what you have in the optional of homework。

It's a reasonable answer exercise。😊，They always spoke about ni where we'd seen nips the whole time。

There are also。Many several lectures where we have talked about LC3B and also there are a few exercises in the homework。

Yeah， and in this homework three， for example， there are at least three or four。其。我我同明年这个承保。

You I ask about like some of this structure something。等下。Okay， yeah， I。

You should know like you should just ask Joness and how exciting the program is。Okay don。这必问题现在问答呃。

What parameters does NST U S。我哋要攞再。那谁入发。So if， for example， an instruction。也告要去。Yeah。

I cant敢 use this one要告。When we provide the instruction definition。

 we also provide some updates so we this this register。You are the social的。And basicallyically。

 the exam should know exactly what is is doing what。Yeah's， it's on。 If you want to switch。Okay。

Shall we continue or do you have any other questions？Okay， let's go to。Part 2。

And here MIPS assembly for Re mob SV。 So here we are asked to write some code。

 some MIps code that is going to do essentially what one x 86 instruction does and this is x86 instruction is this rep mob Sv。

 The mob Sv part means that we are moving bytes and the rep part means that this is going to be repeated several times。

 This instruction has three registers。 there is one count register。

 this E X and then we have one source register and one destination registers register this source and destination are two pointers to two different arrays and what this operation does is for several times and this number of times is。

The content of this register ECX， what we do is copying by by byte from the source array to the destination array。

 and after each of these copies， these two ESI and EDI are incremented。So part A in this question。

Sorry，s from here。Okay， part A in this question。I's asking about how to implement these in MIPS。

So yeah， this actually has some similarities with the first part in summary。

 what we are going to have here is。If we， let's say we write the high level language code for this instruction。

 we would have something like this， right， E， C， E。嗯。Greater than0。

 because E C E is the counter right， where we have the total number of bytes that we need to copy。

 And this would be something like E V I。EC E equal。E， sorry， E S， I。EC C， X。

 this E X would be like all counter and also index to this arrays E S I and E DI。

 And after every iteration we decrement。 So this would be like the。

 let's say the high level language called to implement this rep mop。 and。

And here what we have is the MIPS code there are， we assume that ECX is stored in Reg 1。

 ESI is in Register 2 and EDI is in Register3。The first thing that we do is checking what's the value of register one。

 that is the value for counter。 And if it's not0， we will go to the loop。 And in this loop。

 as you can see， we load。1， by。We store。This by in the corresponding memory position。

 these memory positions are determined by register2 that is EI so they point to the source array and this one register3 is the pointer to the destination array so right after that we increment register2 and register three to point to the next byte and we decreement register one that contains。

Easy x。 So it contains orcon。 And after that， we check。So we check what's the value of ra one。

 if it's still greater than0， if it's greater than0 we。Jump。

 we branch to the beginning of the low body。 If it's not。

 then we go to the rest of the code to the following instructions。

 So its very similar to what we did before。 And I think it's quite easy to understand。

 So don't know if you have any questions。🎼So let's continue and go to the two part B in this second part of the exercise。

 it says， what is the size of the MEPS assembly code you wrote in a？🎼In bys。

 how does it compare to Re mop S V， And it says note Re mop S V occupies2 Bs， right。

 So this Intel E 886 instruction occupies2 Bs。 And the question is。

 how many bytes occupies in memory， this cult that we have just written was， you know， it mes every。

Instructuction。It's a star。In 4 bys。 And if you count the total number of instructions， this is 7。

So the total size of this code is 28 bytes compared to the two bytes of the original instruction in the E86 ISA。

Let me finish with this question and then we take our 15 minute break， is that okay？

We will finish very soon。So part C says， assume the contents of the X 86 register file are as follows before the execution of this instruction。

 and these are。Or registers， the content of these registers。And it says。

 now consider the MIPS assembly code that we have just written here。

How many total instructions will be executed by your code to accomplish the same function as the single Re Mo SV in X86 accomplishes for the given register state so the given register state is this one here and as you can see this register EC has this value this is extra decimal representation but if we convert it to decimal representation is this number here so because this EC register。

 tell us the number of times that the loop this loop here is going to be repeated。

The total number of bitetes that we are coping。And the body of the loop has six instructions。

 the total number of instructions executed in this case is six times。

The value of register EC E plus one， because remember that in the beginning of the loop。

 we had this B EQ instruction， so this is our total number of instructions executed for MEPS compared to one single instruction that would be executed if we have an X86 ISA。

Last part， part D is。Exactly the same。 So the question is exactly the same。

 but the contents of the register file in this case are different。

 And if you observe the value of E X in this。This time it is zero， so if it's zero。

We are not going to enter the loop， right， If it's0， this E is 0， this register one is0。

 so we don't execute this loop， this loop body any single time。

 So the total number of instructions that are executed in this case with these contents of the register file is。

Only one is's only the first BQ instruction that you have in the code。



![](img/7176960e250c3a77834f7c411cd3255e_6.png)

Is that clear。

![](img/7176960e250c3a77834f7c411cd3255e_8.png)

Considerr two pipelines of machines implementing Mips， I S A machine one of machine to right。

 we have both machines have the five pipeline pipeline stages。

Very similar to the five basic pipeline stages that we saw in in class。And광 A A6。So。

 the first machine is。Machine one does not implement inter interlocking。

 so it it it cannot detect that dependencies on however。

 it assumes all instructions are independent andlies on the compiler to order the instructions such that there is sufficient distance between dependent instructions。

So is the compiler who have to deal with the dependencies。

The compiler either moves other independent instructions within two independent instructions if it can find such instructions or otherwise insert knobs。

Assume internal register file forwarding。So one instruction runss into into a register in the first half of a cycle and another instruction can correctly access the updated value。

Of the same registering in the next half of of， of the cycle。

 So this is important internal register5 forwarding in this machine。

And we assume that the processor predicts all branches as always take。Okay。

 the machine2 implements data forward wing in hardware。On the Taa flow dependency。

 it come forward and opera from the memory stage。Or from the gridlike stage to the execute stage。

The load instruction can only forward from the grid back stage。

 so the load instruction only from the grid back。Because data becomes available in the memory stage。

 but not in the security stage， like， like other， like for other instructions。

 So assume some internal register file for wording。The same that in the previous machine。

 So the compiler does not reor the restrictions in this case and assume that the processor of pre solve branches has always taken。

Okay， we have the， this piece of code。You have this piece of code。

Loathten store and at immediate and and a branch。嗯。And these are the initial values。 So basically。

 we have。Depenencies here， these two instructionss are dependent。

 We often register two language to register two into memory。

 And these two distractions are also dependent。So we add in this。

 we start the result of the adding in this register one and we compare register  one with register 25。

 So we have register 25 here the content is 25。 so we execute this loop basically 25 times。

Because we yeah， the initial value of register one is0。 So we increment each time in each loop。

 we increment this register。So when the video code is dedicated the machine ground。

 the compile has to re the instructions and certain nos if needed by the resulting code that has media modification from the original。

 So for doing that， I'm going to。To draw the， the pipeline stages。

 I think that is easier to solve in this way。 So we have this load。 So we have。The fetch。Decode。

Execute。Memory and right back。Right， so。To execute in the， in the store。呃。We need to。

We need to have the this register content。So and we see here that we have some internal register file for workinging。

 So we can， so in the same cycle that we write back in the in the load， we can read from the store。

 So at this point in the gray back， we can read from the store。

 and we read registers in the decocode stage。 So we can do this。 So this is the。store instruction。

 This is the load instruction。 This is the store instruction。

 So the best we can do is have the store here。So this is thecode， it should be fetch。😔，诶。Insecute。

I' right back。So we have some bubbles here。 We have two bubbles here。 So let's see。

If we can feel this， right， you have。You can't fetch here。

Which can fetch here two more instructionss， right。

 So let's see we can reorder the next instructions。

 So we see that these two instructions are independent of the previous one。

 so we can insert this addition before so we can put this a here， right， so we can put。This a here。

And then we cannot put。 So the， the branch is dependent on the Adi， the same， so。To read the。

 the content of register1， we have to wait for the this write back， right， so we will need to。

To execute。De code。In they right back。 Let me check。Okay。So。So basically here。

 we have to insert an op。So， this will be execute。And he code execute。有。Oh Im sorry。executeec。

 modified， gray on the last instruction branch。呃。干fe。呃。So this is not very well aligned。

 but this is the difficult phase。 so we can。So when we grab that here。

 we can read the register from here。So， we can execute。诶。Nmbody right right back。

So this v is basically the code that the final code that we need to。

 that the compiler needs to generate to secure this code correctly in machine one。嗯。

Any questions here。ok。So， next question。What its not。Here。But that it is there is。So。

Usually when somethings not。Basically basically。Yeah， of course， you if you can make an assumption。

 In this case， I am assuming that yeah， you can resolve the branch。So， here all。

The processor predict or branches are always taken。 right， This is a very easy branch predict。

 So you can always assume that it is always taken。 So you don't have any extra latency here。 you。

 you can。Yeah。More questionss。So next question is。EWhen the given code is， so I will answer。

You cannot see this， right， okay。So I will let this question to， to the end。

And I will go to the question C， because everything that is is easier in this way。

So calculate the machine code size for the machine code size of the core segments executive machine  one and machine 2。

 So in machine in machine  one。We have basically five instructions。

 so we have five instructions and each instruction is 32 width so or four bys。So we have 20 rights。

And in machine2， we have exactly the same code。 So the compiler doesn't insert anything。

 So we solve the dependencies of power。 So we have four instructions。So you have 4 by 4 wide。

that is 16 by。So point D。 So question。Yeah， isn't that。Isn't that it rules so dont。With的。No。This。

 look， this is this this look is a a dynamical， right， But you only need for instructions。Okay。

 soFor static instructions。hico would split it up in， and Liya just going through it， but would also。

Yeah， you， you， you make a look over these four instructions， right，In that case， if you have。

A loop of an infinite loop， you will have infinite source code that is it doesn seem my sense， right。

嗯。So calculate the number of cycles it takes to circuit the code ceiling on machine one and machine 2。

 So for machine one， you already。Have this product this。This diagram here， right。 This is cycle 1。

 cycle 2， cycle 3，4，5，6。6。7。eight。9， so this is， so this is one iteration of the loop。

 So in one iteration of the loop。To see that you can issue。E5 distraction，5 distraction。So。

 and the next loop can， can start immediately after these five instructions。So。As we have。25 loops。

And we can start 5 distraction per loop。 So we have。125 cycles。But in the last iteration。

 we have to finish。 So imagine this is the last instruction。

 So we have to execute these final pipeline stages that are for additional cycles。Cl four cycles。

This。Yeah，1 twenty9。嗯。他い公す啊。我可以不享。Yeah， this is。So calculate the number of cycles for machine 2。

 So let's go to machine 2。So in machine 2， we have， I will do it。Yes。



![](img/7176960e250c3a77834f7c411cd3255e_10.png)

Yeah就看。So this is are these are in actually these are instructions， right。

 This is the number of instructions。そう。We have to jo。一道？I， I don't think so。

 So it's only the the number of cycles of this loop， right。スを見て。Yeah， you just will， in that case。

 you just will you mispredict， right， but。But your your look will be secured already， so。

You don't care after that，So， for machine to。That's。So。Okay。For're maing tool， we have this code。So。

 we have first， the load。That this。Fdge。😔，The gold is。Right back。Then， we have this store。

So on the store， we seen the definition of。Of the machine tool。That。嗯。

The load the load instruction can only be forwarded from the gray back stage。

Because the data becomes available in the memory stage。So the data becomes available here。

 So from here， we can forward this data。To the execution stage。 So it's a specified。He right。

 the forward。From the memory or rug of stage to the executed stage。So this。

 this data will can be forwarded from the grave at the stage to the execution state directly， right。

 So we have we have this here。诶。Yeah， we have the gold。So we have， basically， we have to store here。

We are not ready to， to execute in this cycle。Because we need to wait for for the data here。

So next instruction is addition。嗯呃。Whi we fetch the addition。

We have to wait because the code stage is occupied。And then， the。嗯。Well， he all missed there。

The other stages。Decode。😔，Execute memory right back。And then the last distraction is the branch。

So the branch can only be fetched in this stage。Because this is occupied by the previous instruction。

So here we have a dependency。嗯。In these dependencies。 So we come forward from the。

From the memory stage， in this case， because this is not a lot distraction。 So here we can。

we come forward data from here to the execution states， right， So we don't need to wait in this case。

So， the question is asking。For the number of cycles， we have 1，2，3，4。five。S， seven， eight。

 nine cycles。So， we have。So we have in each loop。诶。We need a。5 cycles。And then in the final loop。

 we need four additional cycles to finish the the last instruction。

 So basically is the same the same number of cycles than the machine machine Gu and machine to executing the same number of cycles。

129。clear that's possible。一週的拿。就你。On the。That a checking。よゆす？He used cool funding from。Memb。

If you use squ right， then you do bypassing。Memory stage to the execute stage。To me， because。

stage because the。So there won't even be a situation there。

Get the data forward from memory to execute。Because I wouldn't even executed this yet。

 because the value。嗯。The book。代理。So here doesn't mention。

 it doesn't mention anything about the how this is implemented， right。

 So you have to take the information that you have in this in。In the question。

So what the question says is exactly what we did here， right。So how is this implemented in the。

 in in hardware is another question。But。To need be relevant。I mean。

 I would just make an assumption right， I'm assuming that。です。If you have。And a checking based。

I think doesn't make sense。okay， but。Okay， we can discuss later。But yeah。

 basically but here the the exercise is pretty clear in in that sense， right。

 it doesn't talk about how this is implemented in the in the hardware。

 but so just an internal register file for wording。

 So an instruction write into register in the first half。

It can other instruction countries in the second half。

 this is the for register for wording and for the other for wording。

It can forward and operate from the memory stage or from the gray value stage to execute the stage。

 so the load instruction can only be forwarded from the back because the memory the value is ready in the memory stage。

 so in the next stage， you can forward to the execution stage。Yeah。

 so the underneath details are not specified， but we can， we have to assume that we can do this。

 What this is specified in the question basically。So and the last last question is。

So I led this to the end because once we solve all these questions it very easy to solve。

 So when the giving code sentence is is on machine 2 the pen between instructions are result in hardware。

 explain when data is forwarded and which instructions are installed and when they are installed So we already see that we。

诶。Here。And we have data forwarding here and and here。ok。Questions。



![](img/7176960e250c3a77834f7c411cd3255e_12.png)

Okay， so we will continue this question on Taos Sulo。

 And I think Professor Mulo already like showed some example during the lectures， but I think。

This is an important concept that we can go over once more。嗯。可。

So I'll just quickly read the question。 So this is。

Kind of a question that doesn't require too much computation or。诶。

Like too much knowledge exactly about how the algorithm is working。

 but it's asking more about the overhead and like how many functional units or comps you need in your design。

 So it basically defines those properties where you have eight functional units。

And 32 registers and each register is 64 bits wide and now you have 16 reservation stations entries per functional unit and so basically you have a reservation station for each functional unit and you have eight of those right and each reservation station will have 16 entries so this will basically look something like。

Let me see oh this is circ。嗯。Yeah， so basically it will look like this right。

 so you have some functional units here。嗯。Okay， I can't draw very well， but。

You have eight functional units in total and each functional unit。

 each functional unit will have its own reservation station。ok。And we have 16 entries。

In total per reservation station and there are as many reservation stations as functional units。

 right， Okay， so this is so far what the question told us。And also there are 32 registers。

 3 architectural registers， and then again， importantly。

Each entry in the reservation station can hold up to two source registers， so basically。

This is like so this is exactly the same reservation station that we saw that we had in the slides during the lecture。

 Basically here we have two sort of appearance right， and then it has。

Separate attack fields for each source field。I guess you can see it。 And then separate data hills。

So it looks something like this。And the question is asking。

About how many tech converters are there per reservation station entry？嗯。So if you go back here。

So in a single reservation station entry， we have two。嗯。Two tags， right。

 because we have two source opera。And。So we will need。A comparator for each tag。

For each functional unit， right， because in the same cycle。

 each of those eight functional units can produce a result。

 and this result needs to be compared with each of the tags in the。In the reservation station entry。

RightSo we have two texts here and we have eight functional units。

 so basically it means that we will need eight multiple by two times tech comps。Is it clear？

So basically the result coming out from this function unit will be compared against this tag and this tag。

 so same for dysfunction unit right so it will need to be compared against those two tags and the same is true for all functional units basically we will need two competitorss per each functional unit。

Then the answer is。嗯。8 by 2， which is 16 tech computers per reservation station entry。Okay。

 is it clear？And then the second question B is what's the total number of tag comparisons in the entire machine。

 So this is kind of。Like tricky because if you just think about reservation station entries。

 you may not take into account the rat register A table because it should also have some comparatives because when you calculate the result。

 you don't need to only update the reservation station entries， but also the register AS table。

Which is not shown here， but if I draw this， the register A table will be basically。

It will have 32 entries because we have 32 architectural registers， and then it will have data field。

For each entry。It will have some tag field。Right， and it also have some wallet beds。嗯。Okay。

 so basically。We also have some competitorss here， right， so one compare for each tag。

And then it will again multiply by the number of functional units， because in a single cycle。

 we will need to compare those tags against each of the results coming out from the functional units。

Okay， so if we like accumulate everything together， so we have 16 type compresss for each entry。

Right， and we have。嗯。You have 16 entries。In a single reservation station。

And then we have eight reservation， Yeah， you have eight reservation stations in total。 Okay。

 so those are the total number of tech competitorss for the reservation stations for the registered L table。

 will also need 32 multiply by 8 comparisons。 So here 8， again。

 is the number of functional units we have。Yeah， you can conclude this。Okay。

What is the minimum possible size of the tag。 So this depends on how many。Entries you have in your。

In your in your all reservation stations right， so as we show here。

 so you may have in a similar reservation station， you may have 16。

Enries for which you can do some computation and produce a result， right， so。嗯。

So you can like remember this from the slides that we address those as A，B。

C and et right so basically those are the addresses of those entries and you need addresses as many as the total number of entries you have in your system。

So there are 16 entries in a similar reservation station。嗯。

And we have eight reservation stations in total ride， which makes 128。

So this is the number of address this is the address space that we should be able to address And basically。

 this is equal to to the7。 and this means we we need seven bits。嗯。As a tag。

To be able to address or refer to all reservation station entries。So the minimum is 7。 Of course。

 you can have more than 7。 but then you'll have some redundancy， right。Some useless little sps。

I guess nobody has any questions。Okay。And then what is the size of the register As table in bits。

So the registered El table is。It should look something similar to this thing here that I draw right。

 so we know the tag that should be at least seven beds。And then the data is given in the question。

 so the architectural registers are 64 bits wide。So then per entry， we all need 64 beds。

And I wish you have at least some valid bit， right？So for a single entry， we will have 72 bits。

And we have 32 entries in total， so it will be 72 multiplied by 32。And that goes。

So just let me check if I'm missing anything。Yeah， I think yeah， that's said。

So this is the total storage needed for the registered L table。

And then the last part is what's the total size of the tax storage in the entire machine bits。

 so I'd only ask about tax storage right now， so we should include the tax storage in the register early table as well as in the reservation stations so in the reservation stations we have two tag per entry right so it is 14 bits because we know the tag is  seven bits so it is down 14。

Multiply by 16 because you have 16 entries per reservation station and there are eight of them right So this is the text storage for the reservation stations plus the text search for register earliest table。

 which is 22 multiply by7 right we have only  seven bits。啊。In each entry。Okay。I this is correct。

The total minimum size with text storage and entire machine bit。Okay， yeah。Okay。



![](img/7176960e250c3a77834f7c411cd3255e_14.png)

As in clear， I think this was a relatively simple。Okay。

 the next question is on auto of audio execution。 We solve a very similar question during the first discussion session。

 if you remember。 So this is basically testing your knowledge in Tommou's algorithm。

And I will just highlight a few important things here in the question。

 so there is a one cycle fetch and one cycle decocode stage。

And this machine can execute two different instructions， add and multiplication。And。

Each of those take different numbers of cycles in the execution unit that they are executed。

 so those execution unit， the other and the multiplier are not pipelined and the addition takes two cycles and the multiplication takes three cycles。

Let me see quickly if there was anything else that was important。嗯。I guess not for now。

 but I will refer to to the text here in the question later。 So they let me。

Let me move to the questions。 But before that， so these are。

The state of the register L table rat and reservation stations at the point where all the instructions are fetched。

 And this program has four instructions， which is also highlighted here。Okay， so and， and the。

 this is the sale of those structures after dispatching all of those for instructions and dispatch happens during the deco stage。

 It's also written here in the question。So， the first part。

Is to find out what are those instructions， including the destination register。

 the type of instruction and the source opera here， the source registers。

 So Ill fill the table here on this side so we can like， see everything in one place。

Okay so so the first part is very simple， like figuring out what are the instructions。

 you basically look at those tags over here in the reservation stations and usually there's a dependency which helps you figure out like which instruction comes first and which comes after。

So from the question， we know that the instructions are issued today or。

The instructions are allocated to reservation station orders。

 reservation stations in top to bottom order。Okay， so here。

 when we look at a single reservation station， we know that this instruction comes before this instruction in the program order。

嗯。Okay， so， so we have to start by looking at the first entries here in the two reservation stations。

 So we can easily tell that this instruction over here， the multiple location comes first。

Before this instruction over here， because this is dependent。On the multiplication， right。

 So the D tag is here as a source opera to to this addition instruction。 Okay。

 so the first instruction is multiply， what is the destination register。 So for that。

 we have to look at the register L table， right we don't see any D。

 which means it is overwritten by the next one of the next instructions。

 So we have an instruction that comes after this multiplication that write to the same destination register。

 So let's call this destination register X for now， since we don't know what， what that is。

 And the source registers are。R 1 and R1， which we can tell based on this information here， right。

 So the day the source of is valid and it is5。 and only R 1 has its value set to 5。

 So the two source of are R 1 and R1。So next instruction would either be this one over here。

Identified by tag E or the instruction that has tag A。So here。

 deciding which one comes first is again， very easy because we have a dependency to a here。

 So a should come first， right， and。The second instruction is add。It writes to our one register。

And its source opera are one of them as。So it's dependent on this instruction。

 So this should be the sources should be the same as the destination register of this instruction。

 right， So it should be X。And then the next source register is 8。 The value of the register is 8。

 which corresponds to R 2。Okay， and then third instruction is either B or E。

 And since E is dependent on B， we can tell that the third instruction should be B。

 which is an addition。Which write to destination register for。R 4， and the source opera are air。

 A and A A was writing to R 1。 So the source registers are R1 and R1。And the last instruction is。

Multiply rights to our tree。And source registers are R 1。 And B was writing2 R 4。ok。Yeah， so those。

 this is the program basically。 And we couldn't find any clue like what is X here， right。

 So it could be R1 since。R 1 is overwritten by this instruction over here， or it could be R 4。

 or it could be R 3。 So it could be any of those instructions and nothing change based on like which register you put here。

So， so like let's say， is R1。Like when we do the next。Next part of the question。

 But you can assume this to be any of those three registers， basically。

Or maybe you can just leave it as X。But， basically。In the solution。

 you have to make it clear that you understand that this could be any of those three registers， okay。

So just like， don't just leave it blank。And put something like X and explain that it could be like one of those three or four registers。

 It could be one of the three。Okay。So this is a program。And yeah， we are done with part A now。

 And part B is。Basically simulating that program on the processor that was given。

 And we have to fill this chart over here。 So let me quickly write these instructions here。嗯。So。

 it will be easy。This was our1。This is our1。Or one or two。

I should have written those here are for our。What true four。Okay。

 and then we have to fill the rest of the table。 So we know that this processor has。

A face stage of one cycle。 It has decoed。 multiplication instructions are。Executing in three cycles。

So we will have three execute stages in here。And then。And we have right back。Okay。

 so this is the first instruction。 The second instruction we can fetch here。

We can decode and dispatch here， but since it has depend tendencyency。

 it has to wait until the end of the right stage to execute。

 So it will start executing here and will do right back。 So in the question。

 always like this information will always be provided。 So try to find this part to。

 to determine whether。Execution can start at the same cycle in which the destination register is written。

 or it can start after it。 So in this specific question， it cannot start。 So I cannot put E here。

 I have to put E over here after， after the right backst。 And that information is。嗯。Let me find it。

Yeah， a dependent instruction can begin execution in the next cycle after the write back if it has all of its opera available。

 Okay， so it's simple。 And then for， for the next ad。

 it is the same so we can fetch and decode it here。 but we have to wait for our one。 So again。

 we have a dependency。 so we can execute it here and write back。And then the last instruction， again。

 we fetch and decod it。And to execute it， we have dependency to R 4， which is this instruction。

 We can execute it over here and write back。And。I feel like I made a mistake。

I think it was supposed to take 16 cycles。 Can you see where I made the mistake。Anybody。Okay。

 maybe it was 15。 Maybe I remember it wrong。Oh yeah， okay。Okay。

It should be three executions and right back。 Okay， that's it。 And we are done with this part， too。

 Let's take a look at the last part。Unless you have any questions。Yep。先后。Frection。

It leaves equal to stage。是それく是し。Yes。Yeah， so this is slightly different from in order execution where usually we do the register fetch。

 fetching the source of appearance at the deco stage。 So here that's not happening at deco， right。

 So you are not accessing necessarily the register file at deco。

 You are just like allocating a reservation station entry and filling it accordingly with all the dependencies。

Okay。And the last part is。嗯。Updating those two structures。嗯。

Based on how they would look at the end of the 12th cycle。Basically， here。

So what happens at the end of 12 cycle 12， this instruction completes this instruction completes。

 and this instruction also completes。 So in the reservation station entries。

 we should only have this fourth instruction。Right， other entries should have been cleared。

Let me see if I can put this side by side。Almost。Okay。I hope you can see it。Okay。

 at least we can see the first bar。 Okay， so we know that this was the first instruction。

 This is the second。 This is the third， and this is the last instruction。 So this is finished。

 So I'll just put dashes here at the end of cycle 12。呃B。Is also complete。D is complete。

 So we don't have to fill anything here。 And for E， since a is complete。

 it will have its data available here。 The value will be set。 B is also complete。

 So this will also be set。 So let's find out what are these values。

 So the result of this operation 5 by 5，25， right。 And so D is 25 plus 8 is 33。

 So whenever we see 33， we can put whenever see A， we can put 33。 And then。Okay。

 so basically here we， we will have 33 and B will be 66。 Okay。

 so I just executed those instructions quickly。So this is33 and this is 66。

 and the rest is also blank。Okay， and to fill the register L table， it is again， the same thing。

 we already had calculated the values。 So we know a was 25。 So this will be updated to 25。嗯。

Our two is untouched。Our tree。Is set by this instruction。 It's not complete yet。 So， sorry。

 this is E。 This is 0， and we don't have the value。 And then our4 is。B。Which is 66。Okay， that's it。

 basically。 And this was the last part。Okay， just like when all this question。

 just be careful to read that part carefully or like， you don't have to read it at once。

 but be careful when you need like。To like， make sure， like， what kind of information is provided。

 for example， when you realize this part， like whether you can put E here or you have to delete one cycle。

 you have to like， go back to the question here and look at what's provided。Any other questions。

Then we will continue the next one。 Oh， there's a question。3。Sorry。Be very opinion。A。Yes， yes。

 youre right， okay。This is。A， I updated it by D。咱。Like we know。三名四点。Okay。Today， so do you。

Just pick out the one。So like， I can answer this question， like based on last year's like exam。

 there were students that like， were able to solve all the questions。 So when we design questions。

 we try to。Make them soluble in， like。Approximately half of the time we are providing to you。 So。

 yeah， so we， we can usually solve those questions in in one in an hour if you are providing you three hours。

 Okay， and here why we are still at 60% of the questions is because we are also explaining them to you。

 So if I was solving this question by myself， I wouldn't have been talking， right。

 and then spending time of like。

![](img/7176960e250c3a77834f7c411cd3255e_16.png)

Basically， putting things in a way that you can see and understand better。

So those things also add up and also answering your questions take time。Okay， yeah。没个是。Yeah， I think。

 I think you can check。The links that we have in the website for the past courses and then from those past courses you can check links for like even older courses and then you will find like a bunch of exam questions。

 bunch of homework questions and you can also take a look at the architecture course。

Not only the digital design  one。 So some questions are similar， basically。

We will continue with the next question， which is on out of order execution。

So hopefully you remember the concept so I will go quick over this so here's some definition of what kind of instructions we are dealing with in this question。

 so we have two types of questions， one is add which has this number of cycles here and those stages defined and。

O。Okay， yeah， as I said， so the a instruction has those stages here。

 I think in total it's nine cycles， yes， it says it here。

 and then for multiple instructions we have 11 cycles in total。

 so two more cycles in the execution stage。And the question is also describing it well。

 like what is the。Policy for for reading back the data。

 so it is basically when you have depend data dependence between two instructions。

 the instructions that depends on the result on the previous instruction has to wait for the data to be written in the right back stage and in the next cycle it can start executing。

So the question has multiple parts， one of them is figuring out an instruction sequence that's composed of five instructions based on the information given in this table。

So this part is how the values in the register file looks like before the execution of five instructions and this is what happens after executing those five instructions。

Yes，In the previous question， we said that if there is data dependency。

 we can only start a decode after a Wi finish now we're assuming that。And start executing。finish。

Right， so that's because of the difference between in order execution and out order execution。

 specifically with the Tommo Sos algorithm。So here it is different a little bit， so you will see。

 as we like all the question， but basically here the decoding operation consists of allocating an entry and filling the entry in the。

In in the。Not register earliest table， so you also update the Reg earliest table。

 but you also update the reservation stations right so I can show you like how it looks here so probably this will remind you from the slides you saw in the class。

Okay， so basically the decodder person here is allocating that entry。

 but when we talk about like in order processors， then decoding mostly means reading the values from the register file。

 and obviously you cannot read the values before writing the new values into there， right。Okay。

So here how you can figure out what the instructions are just by looking at those two tables here。

 like before and after version of the same table actually， so there's a hint in this question。

 which is the fourth instruction is given to us partially。

 we only download' know the destination register but we know that it is the multiplication of R6 and R6 right and when we look at before and after version of the register file。

 we can see that R6。Is not modified， right， It remains at 10。

 So we know that the result of this multiplication will be hundred， right， but we don't see hundred。

Anywhere in the register file， right。So someone， some other instruction。

 has overwritten this hundred， right。there is only one possibility because we have only one instruction coming after this multiplication instruction here。

 so we don't know exactly what is the destination register， but just by considering this information。

 we can tell that the destination registers of those two instructions are the same。

Okay so let's start one by one。 so if you look at those given values and the final values we get。

So basically， your approach here should be trying to reconstruct the final values using the。

Using the values that we have initially。So for example。

 we can see that our7 is updated right so it is 21 here， it was 11 here。

 so we can basically look for values here in this like initial version of the register file to calculate this value of 21。

So here the only option for doing that is adding together 10 and 11 right so we cannot multiply 11 and1 because we don't have one in the in the register file。

 So one instruction then should be。And add。Which。Right to our 7。And。

Uses R6 and R7 as source registers， okay？So this is basically creating 21 in here。

So let's look at some other values that has changed。

 So here we see 31 in registered  tree and the original value was 7 right So now given that we have 21 here in R 7。

 we can calculate 31 by doing an addition another add instruction right so we will be updating our tree。

And we will update it by。So it will be again， R 6 and R 7。Okay。So we did that， too。

Other values that are updated this are0 and R 2。So for our0。Yeah。What we can do is。

So we already calculated 3 to1 here and we have 10 and we have the multiplication instruction so we can multiply those two registers and write the result to our zero。

 so it will be a bit ugly。 but this is the next instruction here actually。

 so initially when I was like solving this question。I I was just writing down those instructions。

 but I decided to figure out their order later based on some other information。 Okay。

 so here what I am doing is only just writing down instructions that I can figure out by looking at the table。

 but it happens that all those instructions have dependency between them。

 So it's very easy to figure out the order okay but if it's a bit more complicated which I doubt that it will be in the exam questions。

 then you will need to look at。Some other information that we will be given to in the question like。

The entire five instruction sequence completes an I cycles。Okay。

 so then you may end up with different orderings between those instructions and different orders will result in different execution times。

 right， And then you can find the correct ordering by looking at the number of cycles。 But anyway。

 so if you continue here， we said that we can get。310 to R 0。By multiplying。A tree， and。And。

So this is multiply R three and R6。Okay， and then we know that we have something here。

 So this will be the fourth instruction。 and finally， we will need to calculate。

 So we also updated this。 We will need instruction to to calculate 410 and it is basically the additional 310 plus 00 right So this is already giving us 100。

And we know that we need to write the result here to R2。

 So this instruction here should be modifying R 2， right， so's。Write it here again。

 And then I will fill this。 So it will be updating our two。And it will do so with。Adding to our0。

 it will add 100。 So this instruction here will give us 100， right and。In the beginning。

 we said that it should be the same as this instruction that is following it。So that instruction。

 the last instruction should also be。Are， our 0 plus R 2， right。 So if you feel this here。

To have everything in。Written a nice way， so this was the first instruction， this is second。

This is third。This is Ford， and this is the last instruction。 Okay， so this is add。To。2 7。R 6， R 7。

Then， another ad。To or three。And again， our 6 and our 7。And the loss is here， multiplication。R 0。

 or 3。And R 6， okay， is it clear， did I miss anything？Okay， so that was easy。 so in the next part。

 actually I also hold B and C together because they are sort of related。

 So basically in parts B and C， we have to execute Tommoso's algorithm with this instruction sequence that we find in part A。

So basically it will be filling the Reg ElIS table。Which is this here。

 the register file and also the reservation stations。So， let me。To like this。可 you can see it。

It's better。Okay， you can see almost everything。One thing I forgot to say。

 it is asking specifically about the state at the end of cycle 8。So actually。

 first it will be better to figure out。What has happened inside the processor until cycle 8 or at the end of cycle 8。

So here in the beginning， we were given with these stages。

That the addition and multiplication is going through。 So I will just。嗯。Write it here。

 So in the first cycle for the edge instruction， we will do fetch and then decode。

 and then will go to E1 E2。E tree。If。E 5， E 6。 And then it will be right back， right。

 So this is the first cycle， second。34，5，6。7even and 8。 Okay。

 so cycle 8 is where we are in the last stage of execution for the first instruction。 Okay。

 so then at the end of cycle 8， we have no updates in the register table right in terms of final values here because we didn't perform any ride back yet for any of the instructions。

But what happens is until then， if I write it quickly。

 we have enough time until cycle8 to fetch and decode all the instructions here。

So we can fetch and thecode the second instruction， we can fetch and the the third， the fourth。

And the last instruction right and we are still at cycle 7 here or so this was6 right， 7 and8。

 so somewhere here at the end of cycle 6， we have all the instructions decoded right so we fill them to the reservation stations。

So I'll sort of do it quickly， but if you basically follow。Follow the。Follow the scheme here。

 You can fill the reservation stations and register rail is table one by one。

 So for for the ad instruction。 So we know that at the end of。Cycle 8。

 we will just have the information recorded in the Reg all table and the reservation station and nothing else right sos let's fill this part first So here we have the valid tag and value fields right Do you remember what those means So tag is basically when you don't have the result result calculated but the result will come from another reservation station entry。

And the tag is basically the ID of that reservation station entry， ABC for the addition unit and X。

 Y， Z for the multiplication unit。Okay， so for the first instruction， we have。

The up to date versions of R 6 and R 7。In the register in in the register file， right。

 So for those two source opera， the valid bit is one。We don't have any tag。

Because we are not waiting for the result to come from another reservation station entry。

 And we have the values。 We can just look up from the。From the register file， 10 and 11。

 so 10 for R 6， 11 for R 7。Okay， and then the next instruction is add to R tree。

So it uses our six and our7。But our7 is updated in the previous instruction， right。

 so this time we cannot read our7 from the register file。So， although the first。

Source opera here will be again，1 dash and 10。 So not tag。 and it is valid for the second opera。

 We will have0 as a valid bed。 And then we will expect the result from a reservation station entry A and we don't have the value。

 Okay， so when this instruction in a completes。It will update this fill over here。Okay。

 and the next instruction is multiply。 So for multiply， we don't have R tree。

 We are expecting it from here。 We don't have R6。Sorry， we have our sex in the register file。

 so it will be0 and we will get our tree from B。We don't have the value， and for r6。

 we have the value， which is 10。Okay， is it clear so far？

So you basically continue in the same way for the second multiply。We have the our 6 volume the。

 So well just have。The value but set and the value here。And for the last instruction。

 we all get the first source opera from here， which we put into。Reservation station N to X， and。

Our two will come from。Reservation station entry Y。Okay， so this will be x。 This will be Y。

 Both are not valid yet。 and now you don't have the value。Okay。

 so we kind of did it did it deco coupled。 But at the same time。

 when you are filling those re reservation station entries， you can also update the register L table。

 But it was difficult for me to fit both pieces of paper at the same place。If I do it， can you。Nice。

 okay。So this is easier to fill。 So basically for R 7， we are updating R 7 here， right。

 We will have wallets set to0。And the result will come from A， right。

 because this is where we put the。Which this is the reservation station entry allocated for the first instruction。

 and we don't have the value。Or or。You can preserve the existing value right so we can just write here 11。

 but it is really a don't care value because we know that it is not valid because of the zero here。

 Okay， so it is both fine to write nothing here or just to keep 11， the previous value。

Okay and then the next registry update is R3， so for R3 again we will have zero because none of the operations are committed until end of cycle 8。

And。It is allocated to B。Okay。And then our0 is， again， not valid， and then it's allocated to。

Preservation station entry X， our2 is allocated to y。And our trees is， again， ared to。C。

 so here you basically update this again。 Okay， so we don't have why in the register A table。

 but we have why in the re station entry over here， right， So when。嗯。

When this instruction over here y completes， it will not update the register file。

 because the most up to date version is supposed to come from C from the next instruction。

 but it will update the corresponding reservation station entry over here。Okay。

So if you do everything sequential， you will see that every instruction is getting the correct value and you have the final values in the register file。

Okay， and and the rest of this registered L table is basically the same as the same as the before here。

Yeah， wouldn in this case then make sense to。register AS table from the bottom up based based on the reservation stations because then we could never run into issue。

 we write something in the Reg AS table and time to figure out oh， there's a new room。

 would make sense to write it from the bottom up。Yeah， you can do that。

 but so how Professor Mulu was like doing this in his slides was so whenever you first allocate a reservation station entry。

 you also update the register release table， so it is totally fine to do what I did here to initially put a tag there and then when the next instruction comes and overwritedes that destination register you update as well。

 so it is actual what happens inside the processor right because you do one operation at each cycle。



![](img/7176960e250c3a77834f7c411cd3255e_18.png)

Okay， cool。

![](img/7176960e250c3a77834f7c411cd3255e_20.png)

So the question is about building logic and also through tables， as it also writes here。

So in this question we have four inputs and also two functions which are directly related to these four inputs and we are basically asked to fill this table and also write the boolean formula for x and y here so these are these are our inputs a3 to a0 and these are our functions that we're gonna fill the through table here so let's look at the first you can see it right so let's look at the first question here the first question it says describes x first and what x is basically x is1 when the input basically the all of the inputs does not contain three consecutive ones in words a3 to a0 or otherwise in other words it is0 when it contains three consecutive ones basically so let's find such occurrences in this true table so for。

ForEx example， it contains three ones consecutively right。 So then this means that here x shall be 0。

And we also have three consecutive ones here。 So here also x should be 0。 Allright。

 And the last one should be yeah。The last one is here。 So this is 0。 for， but for the rest of these。

 x will be one Y， basically for the rest of them， I won't have any three consecutive ones。

 and that's just。Very quickly， write this。Allright。Okay。

 so and the question says we fill the table and fill the true table and use product product of sums。

 This is product of sums form to write the correspondingent billion equation for x。 So basically。

Let me。I it。So what a product of sum is is。We have。嗯。So， we have。We have terms。And those terms are。

I'm sorry， sorry。So for x， we have such terms and those terms will be handed to each other。

 This is basically the product of sums。 and here I will have the os here。

 So what products of sum says us basically this X。Will be one if all of these terms are one， right。

 Or in other words， this x will be 0。 if one of these terms is 0， basically。

 So I'm gonna pick the second option here， because it is。

 it will be easier for me to write the balloon equation Y， because I have fewer zeros。

 and I'm gonna write my equation accordingly based on that。 So basically， I'm gonna try to make x 0。

 if， if those terms， if one of those terms becomes 0， basically。I'm sorry。

 so I didn't try anything yet。So let's， so let's first thing。Think the case when a3， A2， A1 and a0。

Is 1，1，1， And I will have 0，4 x， right， So in order to have this， I need to have a term such as。

A3 knot， A2 knot。A 1 not and a 0 not， right。 And if all I I'm sorry， and I have。Or here as well。

 So if I have one for all of these， then this will be0。Another term。Will be for this。 So what。

 what it， what it is is basically8，83， a 2。A1 and a 0 is 1，1，1，0。

 So how can I write it in a term is basically。A3， n， A2， n again， or。A1 not and a0。 So if you put 1。

1，1，0 here， then this will become 0。And the last one is， basically， that one。

So I'm going to directly write it。 Hopefully， you understood the logic here。 So it will be。A3。

 a2 knot， a 1 n， and a 0 n。Okay， and those are ended， and this is x。

 and this x will be 0 if one of these terms are0， basically。So this is the solution for A。For B。

 it asks for the。Some of products。And why is basically is one when no two ages and pits in the world are the same。

 Basically， what it means is that。Basically， I won't have an agescent input bits equal to each other right so this means that here where is that yeah。

Here I don't have any adjacent inputs equal to each other， so this should be one。

And I guess here yeah， here I also don't have any adjacent input equal to each other。

 then this should be one and then rest should be zero because for the rest of the cases I will have at least one two adjacent where inputs equal to each other。

R is0。And。So what is some of products is basically I have terms， those terms are ended。

 inside ended and outside those are art。Right， so again， like in， in another words， So y is one。

 if one of these one， basically， So let's then write it in that way。 So to make y1。

 I have two options。Either that。Or that's right。 So this means that。Why is。Or。A3， a2 note， a 1。

And a0 not。 So this is similar to each other， but instead I or the terms here。

 and I said that if one of these is one， then why should be one。

 This is what the question is asking for basically。So。I think there's no question as that。So， for C。

All right， so for C， it says， please。Yeah please represent a circuit of y using only two input exs and end gates。

So this is， this will be， I'll write the circuit in a very intuitive way。

 and also I'll show you the equation later， but very intuitively how you should be thinking is basically for why。

So I don't I shouldn't have any two adjacent inputs equal to each other right。

 So this means that those are basically exhausts right， So those shouldn't be equal to each other。

 So then how can I write it。In that manner， is basically。

So this ensures that those two inputs won't be equal or it will give one when those are not equal to each other。

 let's say。For this one。This says that a2 and a1，1 A2 and A1 is not equal to each other。

 then the exor will give us the one again， so this is ex。And for a0。

 probably youll see where I am going。And here， similarly。

 this exor gives one when these are not equal to each other。 So basically I'm going to end those。

 right。Yeah。哦。Oh。And this is our。Very intuitive circuit。So if you need to provee that。

 this is actually correct。I have。Something written here。😔。

So what you need to do is let me see if you can see it here。

Yeah what you need to do is basically you need to write why in in a Boolean equation and also take the de organ right and so when you take the de organ you will have something like this。

So， you can。Distribute those in such a way that those。

 all of these will be cleared and the rest will give you some bunch of eggsnores and eggszos。

 and some of the eggszos or eggsnores will be implicitly included in other eggss。

 and then you will also end up。With the same circuit。All right。

 if you don't have any questions related to that， we can take a break。Yeah。I'm sorry。不。No。

 the question asks for you the circuit， right， So if you show the circuit。

 but like be careful like what make sure that you do， what the question is asking for。 For example。

 if the question say that use the Boolean algebra。And not， for example， Kmap， don't use Kmap。

 but use bonus such as like those are the details。 but if the question is asking for the circuit。

 it's enough for you to show the circuit。

![](img/7176960e250c3a77834f7c411cd3255e_22.png)

![](img/7176960e250c3a77834f7c411cd3255e_23.png)

It's about data。Do you remember the dataflow， So it was kind of early in the lecture。

 I think it was I don't know exactly which week， but it has been a while probably you're not looking at data flow machines。

嗯。So this question asked for Fibonna function implementation， right。

 and it gives you some notes here that you can use。

 such as addition and greater than opera and than copy and branch。

 So you're allowed to use only those。 And also you can use constant inputs。嗯。To feed to your notess。

And that's it。 So using those nodes， you all need to implement Fibonna。 So just say。

A quick reminder of Fibonna。 So it was it is a like series of numbers， which goes like01。

1 and then two。 So basically each number is except for F0 and F1 each number is the sum of the previous two numbers right。

 So basically the next number is one plus 2。And the next number is 2 plus 3。And then 8， then 13。

 and goes like this。 So F 0 is 0， and F1 is1。 So this is by definition。And the rest is。If an。

N -1 plus F-2。And so you can implement this in a recursive manner， but it is。

 I guess more difficult in data flow， so just the iterative version is I guess easier。

Where you you will just basically do it， as I showed here， start with 0 and1。

 And then the next number is the sum of the previous two numbers。So here in these questions。

I guess it makes more sense to start simple like to start with part of the question but not to like design everything the entire data flow at once。

 so you should do it really step by step so the first step should be in this question making the data flow engine work for n equal zero right so for n equal zero your data flow engine should return zero because this is how FCO is defined。

Okay， so。Let's start with some input and， So Ill。I did here， okay。So we have n。

 So well assume that this is0， right， but it could be anything。So let's assume this is 0。

 And so the first thing we will need to do is to compare this。

Against zero right and basically here we will try to make this work only for the case where n equals0。

 but still we will need to compare this right。And then if this is equal to zero。

 this what we will do as。So I don't want to connect this directly because we will do something else later。

 so I will do a copy here in advance。Because we will copy this and somewhere else。 But okay。

 let's do it like this right now。Okay， so we compare。

 so we know that here the result will be false because n will be equal to 0， but not larger than0。

And then so this will generate some flag， right， So let's also copy this flag。And then。

The next thing we will do is so if the result here is false。

 we will basically will need to return zero， right。And then this is simple。

 so we'll just basically put here a branch node and then feed this in here。 and if this is false。

 so this is the false pad。Right。Zero here， which is hard codeed。Should be directed to the output。

 right， And if this is true。You should just consume this， but do nothing。 right。

 So we just consume the zero。 And then the rest of the logic will do something else。 Okay。

 so basically， so here， just with this data of flow， it is working fine for n equals to  zero case。

 right， if it's0， it returns 0。 if it's not。If I is not sure， it just not doing anything meaningful。

ok。So the next step is making it work for other values too right So for n equals 1 each is your term 1。

 so we should do something else to implement that case， so let me put T here。To indicate the truead。

嗯。Okay， so the next thing we will do is。 so since we here check the。Check the first iteration。

 We will need to decrement n if it's larger than zero and then continue itating。Okay。

 then you already have the copy note here。 So we will。Copy this。To a branch noded。

And then this branch node will be controlled with this same。

Flag here that was generated previously for N， right， and then。Basically， if this is false， right。

 we should do nothing with this N， which is forwarded here， or we should just consume it。

But we shouldn't do anything because it's always zero。

 So the the function should be terminated at this point。So the false pad， in this case， is ground。

And if it's true， on the other hand。嗯。You should subtract one from n。And do the next it。

So this is minus1。嗯。And then basically， we will need to compare this n -1 again， again 0。

 and I see whether it's now equal to 0。 So we already have a comparator not here， but。

So I'll do another one， so I'm not sure if this is this will be possible to reuse this。

 even if it's possible to do that it will be too confusing to understand so I'll just create a new one because this is hardcoded to this output logic here which is receiving zero。

 so I'll just duplicate this。And。And， basically。So this will be n -1 right here， which is coming。

 So this is n -1 in this case。So let's copy this again。And then。Compare this。Agains 0。

And then this is basically the new flag， which will be used for。All iterations， except the first one。

 right， So for the first situation， we will use the， Yes。

 can you quickly recall how the the branch now works。Yeah， sure。 So So branches。

 So it get it has two inputs right， So two inputs should be valid and it outputs either from the false pad or true pad right And basically。

 so one of the inputs is the flag。And one of the inputs is data。So if flag is true。

The data goes through the true path。If flag is false， data goes to the false path。

So token is generated only only one of the output pads in the branch node。Is it clear， okay？Okay。

 so we do this。And then now we'll build our like this addition operation here。

 which adds together the last two numbers in the sequence。嗯。So for that。

 we will need another control node here， another branch node。 which will be， again。

 controlled by the same flag。 So from now， we'll always use the same flag， but。Okay。

 so we'll also have some otherer node here。 And for in n equals one case well just need to add together 0 and1。

 right， so we know that。 So for now， let's just hardcode those values。 So I will draw in。0 like this。

And。We can also draw one like this。嗯。Is there anything missing you're missing。Okay， so I don't think。

 So， so you can ignore ignore this branch for now。 we will connect this later。

 So let's just consider n equals one case right now。 And basically。

 this result should be forwarded to out。If。嗯。Branch。So we have another branch here， this is data。

 and this is control that it is getting。This is the true pad。 This is the false pad。

And this false pad。Sorry， it's kind of ugly， but this false patch should be connected here to the out in this case。

 So basically here what happens is in the first situation， if this flag here。

 if this comparison results in false。The output will be produced from here， right？

 And then the rest of the data flow engine will be will not be active because it won't have any tokens here。

 So I'll show you a quick example of how it works with some random end number。嗯。

But when in the first situation， this comparison generate is true。

 then we won't be using this output logic anymore， right， So the output will come from here。

 So for example， for n equals one case。This will generate false。 sorry， this will generate true。

 right， And then this will just be consumed。 And then this true will go here。

 And then this will cause n -1 to be generated right when if， if this was false。

 n -1 will not have been generated because it's grounded here。Okay。

 N-1 is generated and then it's forwarded here， right， And this is basically the sum 1 and 0。

Whi just forward to the all。Okay， so I think now we have it working for the two cases， zero and1。

 which were the like hardwied vol for Fibonacci。Sequence。

 and now we will just make it like work with any arbitrary N。 And for that， basically。

 we'll create a loop where this result。嗯。Is forwarded on the true pad。Back to this edition。

 was you crying。And then this is basically。So this will need to be connected here。嗯。

But we'll need to forward the same value to this branch logic 2， because this will be the end。

And n minus2 if you will right because so this data forwarded here is just the result of the previous situation n-2 n minus-1。

 but we will also need n my n minus-2 right and then we will get it from here basically we will forward this for here and then copy it so I will put a copy here。

嗯。And then this copy。Is copying thevol here and， and also here to this branch logic。

 and this branch notice。 So this is the false pad。And then this is true pad。

 It generate volume for other iteration。 So this hard code at0 will apply only only once in the first iteration。

Okay， so this is kind of ugly。 But here we have copy node。 And then this gets。1。

 in the first situation。And otherwise， get talking from here from this bad。Okay。

 so is there anything that we are missing。One thing we are missing is this。

 So we haven't connected this here， which is。continuously generates n minus1 n minus-1 for each iteration。

 so this should go here as the data input of this branch。And I think we have all other pads handle。

 Okay， so let's test the case where。And。Equals 2。How much time do you have。Okay。

 so I I I hope I'll finish like in five minutes。 Okay， so let's just test the n equals to two case。

 I think we already verified n equals to0 and1。 It should be obvious here。 Okay， so for n equals 2。

 So we start from here， right， So this is the only place where we have a token ready to execute。

 right， So this is n， which is2。 We know this is 2。😊。

And then so this is being consumed by this copy node right， so I'll just show it like this。

 so this is also forwarded here so we have two on those two places and then this node is also ready to fire because it has all its input inputs rating so we have here streams of zeros and then here we have two and then this node will consume this two and will generate true because two is greater than zero。

And then this node is also ready to fire， and then we will copy through here。

And I will also copy true here。Okay。So we have the flag here， T。 We have data 0。

 So this node is also ready。 So we will consume T here and also this stream of zeros。

And then since this is true， this will do nothing right， because it's connected to ground。

 So basically this single like terminate here and will not be used for the rest of the iterations。

Okay， and now what happens is。What else we have already here？嗯。他不来。This one。Yes。

 it shouldn't have three inputs。So basically here， what I tried to show is those two data inputs are。

Connected to each other。 So it's just shortcut。 So basically a token either comes from this pad from this copy node right or from this copy node。

 So in this case， for the first situation it comes from this copy node， right。

So we have two as data here。 We have。True as a flag here。 so we can also consume those two volleys。

Over here。 And then。When this branch of fires， it will forward two here on this pad right and then have two and minus-1。

 this is also a fire and this will calculate one， so we get one here and then we copy one here and then we copy one here right so this time we receive data from this pad。

And this pad is not producing anything anymore。Okay， and then we consume this one。 This， again。

 generate is true。 And then we copy this true here。 We copy true here。So initially。

 we had0 and1 here for this edition。 So we consumed those two。 This is one。 The result is one。

 and then。This branch node is ready。We consume those two。 And from the true pad， we get one here。

 So this was copy node and un copypy node copies one here and un copies one here。Right。

 and then this branch is ready。 so we consume the true and one and forward one from the true path。

 So this addition in the next iteration， the current iteration gets one and1， right。

 So previously it was0 and1。 So it's one and1。 And then this is being consumed。 We get two here。Okay。

 so actually we found our answer， but this is not directed to the output yet。

 right because we don't have the flag ready here at， so we need to propagate the flag so。Yeah。

 I guess we forgot that pad。 So here， this flag should also be connected here， right。

 So same as the data。 So as data receives。The token from like two different paths。

 So the the flag is doing right。 So here the flag was true。So we get a true here。Right。

 and then this， this true is being consumed。 So basically one is forwarded here。And then。1-1 is 0。

 right， and then 0 gets here and then it gets copied here and also gets copied here。 So this time。

 this comparison node generates falls。Instead of true， right。

 and then this false is copied here and also here， sorry， this is false， right。

 And then since this is false， this is grounded and it's not generating any more tokens here on this bad。

And then we have false here， and then this false is forwarded here， right， which is again， grounded。

 So this just consumes this with whatever data is here。 And then we also copy this false here。

And we had two as a data here。 And this is the false pad。 So we basically forward this two here。

To the output。And we get two for a case where n is2。

 So this data flow may not be like very obvious at first。

 but basically you need to iterate yourself with different values and maybe try different implementations。

 but the main thing that you need to get from here is that concept of producer and consumer right。

 So a token can only fire。 I'm sorry， a note can only fire if all of its input tokens already。

 otherwise， it cannot fire， yes。On top of that， we got the regular。Next然 the。这个在。

Here you mean this part。Okay， we could could。嗯。Yeah， so this is the flag part， right。Oh no， okay。

 yeah， okay。I guess you are right。 so this is basically you should be connected here。

Is that what you're saying？Okay， I guess other questions。ok。Then we can move to our question。

I set so the inputs like 0 and1 they can only use one。I like， how do I decide what to you？Yeah。

 I mean， so here in this notation it's not clear， but so you can do that in a data flow Engine you can define to have like constant stream of some value right so here I think I explained like that so here we have streams of zero so I will show it like the0 so it continuously get zero tokens from this input right。

 but those are just one time values that are being generated only once when you initialize your data flow engine。

So same here， this is also dot dot dot and same here minus1。Okay， so those are all streams。

 but those are ini ball this zero and this one。So this is also stream。

I guess you need to make the notation more clear。

![](img/7176960e250c3a77834f7c411cd3255e_25.png)

Okay。I think we'll continue with other questions。ok。

So the second question is from homework4 the pipeing question。So here in this question。

 we have six instructions given to us， and we need to calculate how many cycles do they take for different configurations of the hardware。

So we have some information here that we are going to use in each bullet points。

So the first question asks。How many cycles does it take if we have a nu plant machine？So here。

So first of all， if you don't see very clear explanations in the exam。

 you can put your assumptions as it's stated in this note two， sorry not summer。Yeah， not to。

So as long as you make assumptions that make sense and you follow。

 youll be consistent across the question， then your solution should be fine。

And here we make an assumption here in the first question。

So in this part we see that when we have a pipeline fetch takes one cycle， thecode takes one cycle。

 execute takes six cycles for a multiply and four cycles for addition and then right back takes one cycle right so what we our reason assumption here is when we run a mole then it's going to take nine cycles when we run add then it's going to take seven cycles。

 so in total it's going to be four to eight cycles when you just add them up on top of each other because we don't have a pipeline in here。

And the second question。We have some configuration for some pipelineing。

 so we are using the scoreboarding technique and in our hardware we have five others and five multipliers and we do not have any data forwarding。

 right？Okay， so one thing we need to be very careful about is a data panel this here。So。

If you look at these registers as noted in this note1。

 each instruction is specifiedifies with the destination register first。

Then this line means you multiply R1 and r2 and you write the result to R3 right and in the second instruction。

 you need the value of the R3， so the second instruction how to wait has to wait for the first instruction to complete and write back the results to the register file。

So I can just actually mark this data dependency here。As you can see， the mo gets sent here。

 fetch decode， and then it has six cycles of execution and then write back。

And when you have the second instruction， you fetch it and then you need to wait until the result of R3 is written back to the register file to be able to successfully finish decode so we have this kind of dependency here after right back we decode and then continue right？

And then you just follow the same。Idea for the other instructions as well so I just put like two rows here because it doesn't fit the whole thing doesn't fit into one line so this is until like 16 cycle and I repeated 15 and 16 cycle here this is just copies of these。

And then you can follow the rest here。 So another dependency we see is。

Between these instructions are seven results and this uses R seven， right？

So this has to wait for this， and it is the same thing we write back and then equals here。

And when we look at the multiply in the last instruction， so it uses r 5 and r6。

And these are calculated by these instructions。Right。

 so these instructions complete in 15 and 16 cycles。

So we already have the data in the register file when we come to this decocode stage。

Then can we don't have to stall and we can just finish executing the program into any eight cycles。

Yes。外据。扣对。我。While easily Q more。地础啊哼。The second instruction。

So this Dcode goes to where in your question。Mind。这个。Third column here。

But you need to finish the execution to understand what is the value of R 3。

To be able to get the R 3 and put it to the。Yeah， but in the decocode。

 you read from the register file， right？So you fetch。

 meaning that you fetch the instruction from instruction cache。 And then in the decocode。

 you read the。So attached the over list in the。Yeah。

 so you need to fetch the opera from register filing de stagess。Okay。

 so in the third part of the question。We have one simple difference here。

 which is we have data forwarding now。And we still have five others and five multipliers here。

 and we are using scoreboarding technique。Okay， so what matters here is。

Now we can get the result earlier than we were doing in the previous part， right？

 So the result of the first instruction is ready here。At the end of8 cycle， right。

 And then we don't have to wait for it to be written into the register file。 and then we read it。

From there right so in this case we have a data forwarding。

 so I just assume that this data forwarding happens from the end of the multiplier or other to the decocode stage。



![](img/7176960e250c3a77834f7c411cd3255e_27.png)

Which gives me this kind of dependence here。 So I can save one cycle here。

 So this decocode was in10 cycle。 Now it's in9 cycle。 And you continue and do the same thing。

 And then you see that at the end， you just save two cycles here。In the third part。

 now we have a little bit more change。So this is like the first case。 we do not have data forwarding。

But this time， we have one other and one multiplier instead of four five of them。

So here actually another assumption comes here we assume that once we start using an error for an instruction。

 then use we cannot pipeline inside this other， so we just give the inputs to this other and we get the output at the end of the fourth cycle or in multiplier case at the end of six cycle。

So。Here。What matters is， So this part is， this R3 is exactly as in the B。Be part of the question。

 but when we have the second a here。Then we cannot start executing here because at this cycle。

 the other is being used by the second instruction。So we need to wait until it's completed。

 and then we start using it from this side。And then once you just follow the same idea and do the rest。

 then you see that now we completed 34st cycle， which means that in the previous one it was 28。

 now we have lost three cycles。Because we don't have additional others and multipliers。

And the last question is， if you do not have， do you have a question？Okay。So the last part。

 the same story， we have scoreboarding， one other， one multiplier with data forwarding。



![](img/7176960e250c3a77834f7c411cd3255e_29.png)

So what we do is basically we just copy paste the result in the D and we just push the cycles back。



![](img/7176960e250c3a77834f7c411cd3255e_31.png)

Based on this data forwarding， which is the same thing we did in the question part C。

 So this is like a bonus here， like three points， right， because it's just some redundant thing。

And if you complete it， you will see that。It's going to complete in2 in a9 cycle。

And that's all of the pipelineing question。 if you have questions， I can。Yes。I think， yeah。So。

 I'm not sure if it's。Very realistic。But it's Cha be O。 I'm not sure。Could you email after the class。

 and I can give you a more term cancer。Yes。就是那小。Which one？This one。来。He is what。我的是马费。

This multip unit。So this is okay， so there's another bottleneck here， right。

 So you have to fetch and decocode these instructions and you have you have a bottleneck over there。

 So the the fetch stage of the pipeline is busy with the second instruction still here。

 so you cannot fetch this。So to avoid it， for example。

 you can go for fetch like multiple instructions at the same time and more complex time。细边佢啲。

Cycle 11 here。So you're asking why this this stalls here。So after fetch。

 it needs to go to decode and the decocode is busy with this here。要的。Any other。No， okay。

 we can go for the next question。

![](img/7176960e250c3a77834f7c411cd3255e_33.png)