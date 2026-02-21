# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p37 -37-  L28_ Problem Solving III (Spring 2025).zh_en -BV1iV1XBWEJW_p37-

![](img/4aaa0601442398c4153434b16b486e27_0.png)

So I'm Muhammad。 I'll continue with the branch protection。

 This is very interesting question and easy straightforward， but a bit tricky。

 So you have to be careful about every sentence here。 So you are given a piece of code。

And it's basically an array of n elements。 And those elements or the value of those elements are truly random generated。

So you cannot predict the value of this element at each index。

And you have three F loops inside the four loop。 And at each F statement。

 you are trying to examine if that value is multiple of2，3， or6。And this is not if else。

 This is very important。Okay， and the question asks you to show out of those four branches。

 so you have B1， which is the four loop， B2， B3 and B4， which are the F loops。

So out of those four branches， what are the locally correlated branches。

 Local correlations mean here for the specific branch。

 If I know the previous value from the previous iteration or or if I know that branch is taken or not taken。

 can I decide on the current iteration， whether this branch will be taken or not。

So this is what does mean a local correlation。So basically， for the first branch。

 I have a for loopbe from 0 to n-1， which means this situation will be repeated n times。

So if I'm in the n-1 iteration。 So I know for sure， the next iteration will be taken， right。

 because I have N many iteration for branch 1。 But for branch 2， branch 3。

 branch 4 are I'm trying to examine the value of the element and the value it says here。

It's completely random。So if I know that the previous value or from the previous iteration for branch branch2 was not taken。

 so I cannot decide， I cannot predict for the current iteration， whether B2 will be taken or not。

 So that's why the locally correlated branches are only B1。So for the second part of the question。

 the same thing， But I'm asked here to find the globally correlated branches。

Meaning that if I'm the current situation and one of the branches is taken， can I decide。

 Can I say something about the other branches， Can I say whether it to be taken or not。So。

For example， B2。 So if the value a that index is multiple of two， can I say something about it。

 whether it's being multiple of  three or multiple of 6。So obviously， if B4 was taken。

Or it's currently taken at the current iteration。 Then for sure， B2 and B3 should be taken。 Any。

 any number that is multiple of 6 should be for sure， Multi of2 and 3。So before before is globally。

Crelatedated。With P2 and B3。Any questions so far。 So very easy。

 Just you need to remember the difference between locally correlated and globally correlated。系呀。这意思。

Important。民国制。啊。I mean， the64 is at the end。好跟谁的。一このよ。保证。So， yeah。

 So this is basically based on the compiler。 So if the compiler decide that B1 is placed before B2 and then B3 and so on。

So when add PC equals PC plus 4， then you go directly to the B4， then you need to predict the。

 the branch 4， whether it's taken or not。 It could be the other way around。

 Could This one could be placed before， right。So anyway。

 the thing here is that if branch 2 and 3 are taken， then for sure， branch 6 should be taken， right。

 And the other way around， if B4 is taken， then B2 and 3 for sure should be taken， right。

 because any value that's multiple of 6， multiple of  two and three as well。So， straightforward。Okay。

 so now for the second part of the question。So this should be B or2， and this is a。Okay。

So now I want to run this piece of code， and a processor that has a global branch predictor。

So I have， I'm given this a global history register that has 2 bit only。 So you could have 3，4。

 But here I'm， I'm only having 2 Bs。2 Bs mean I have four entries。

And for the global history register， what I'm storing here is basically if two branches are taken or not。

 So it could be taken， taken， not taken， taken， taken， not taken and not taken， not taken， right？

 So one of those entries。 So I'm considering two branches at same time。And the pattern history table。

 I'm storing four entries as well。 So for each one of those。

ItCould direct me to to this pattern history table， where I'm storing something here in each entry。

 So I'm having four entries in So this is the global history register。

 And this is the pattern history table， and this is the entry。

So I'm setting all those values here to 0， initially。

And whenever I'm facing or I'm hitting one of those entries in the global history register。

 So I'm trying to increment this by one。 And if it is missed， then I'm decrementing it by 0。

 Or if it is taken， Im increment by one。 if it is not taken decreement by one。

So this diagram is given the other page。Which is here。Okay。所有。

So the question now Im I'm doing this for loop 120 times means means that n is equal to 120。

 So so the question ask me what's the value should be here in the first entry。

 given that that the first record is taken and taken。So there are two branches are taken。

 So what's the probability of the next branch to be taken or not， or in the other in the。

So let's rephrase it。 So what will be the value of that branch， the third one taken。

 then I'm going to increment one。 And if it is not taken， I'm going to decreement by one。

 So what's the final value after 120 iterations。Okay， so I'm having B1， B2， B3 and B4。Okay。

 so now let's assume B1 and B2 are taken。几。😊，What will be the contribution of B3 being taken or not。

To the total value。 So for this question， because given here that all the values are completely or truly random generated。

 So I cannot guess any values。 So for simplicity， I'm going to assume that the values are 1，2，3，4，5。

 and 6。 So this is my array。 So the any value at any element or any index can be one of those values。

 Okay， just for simplicity。😊，Why I select 1 to 6， because this piece of code is always examining the multiple of 2。

3 and 6。 So this range should cover all the possible values。 After that， I'm repeating myself。

 So after 6 is 6 to 12 with the same thing as 1 to 6， right。Okay。

 so remember that maybe I could show it here。第二。So this is B1 and B2。

 So B1 is always all the could be any of those values， right， So6 over 6。

 the probability of having all those values。 So it could be any one of them。

 I'm not excluding any one of those for B2， it should。

 if I take B2 means that the number is multiple of 2 How many of those is multiple of two。3 values。

 right， which are 2，4 and 6。And this has the probability of three out of6。Now。

 for B3 to be taken means that one of those number or all of them or some of them is multiple of three as well。

 How many of those is multiple of three。Only this is guy， right。Okay， so which is multiply。

But by one over 3， which is 6 out of three values， right。Clear， okay， great。 Now。

 this is for the first case where B3 is taken。Given that。

 B 1 and 2 is always taken based on the entry here。 So both of them are taken。 Now。

 for B 3 to be not taken。Which is the other two values。

So three out of 6 multiply by two out of three。So this is taken。 This is not taken for B3。Yeah。

So now what's the total Again， this is it should be in plus。

 This should be in minus because I'm decrementing whenever a branch is not taken。So do the math。

 you will get。Yeah， minus。One over six。Any questions so far？Just add them together。 That's it。

Simple math， right。Okay， so now I'm considering the other。

 the other possibility where I'm having branch 2 and 3 are taken。 And I want to examine if B4。

 the contribution of B4， whether it's taken or not taken。 So B2 and 3。

It's multiple of two and multiple of three。 So I want to check out of those six values。

How many of those are multiple of two and  three in same time。How many。Okay， so which is number 6。

 So I'm having one out of 6 is both for branch 2 and 3 to be taken。And now I'm。

 I'm checking the branch 4， which has multiple of 6。 So we already said that I'm picking this guy。

 which is number of 6。 Now， what's the contribution of B4 to be taken， which is single value。

 which is 6。 So all6 will be taken， right？ So multiply by one。That gives me one out of6。 Now。

 what if before is not taken。If before is not taken means that there is no other values。

 I'm having only one value。So that's why minus-0。And I'm having one out of 6。 Now。

 you can consider the same thing for before。And B1， which are taken。 And in this case。

 multiple of 6 is only one out of 6。 Now， I'm checking if branch 2 is taken。 branch 2 is taken。

 mean I have only 6。 then the thevalue 6。 So it's always multiple of two。

 That's why we multipied it by one。 We get one out of 6。 And we have noment no no。

 no possibility for B2 to be not taken。 So it's always should be taken because any values。

 multiple 6 is multiple of two as well。And the same thing。 So what's remaining now。

 I'm having B1 and B2。To both of them to be taken， B2 is multiple of two。

 How many of those are multiple of two is  three out of 6 multiplly by。嗯。😊，这个是多钱。No。

 the first one was B1 and B2。 and I'm checking B3。 So here I'm checking B1 and B2。Oh， sorry。Yeah。

 so first one was B1， B2。 I'm checking B3。 now， B2 Im B 3， I'm checking B4。 now， B4 Im B1。

 I'm checking B2。And what else？So should be B2 and B3。And now I'm checking B4， right， Okay。

 now it makes sense。So B2 and B3 is multiple of two and3s。 We have only one value。

 which is one out of6。And now checking B4， which is should be  one， the single value。

 Then I have one out of 6。 Now，1，6，16，1，6 is 3，6。🎼-1 out of6。 This gives me2。

6 multiply by the number of duration，120。🎼Yeah。So do the math， you get the value。



![](img/4aaa0601442398c4153434b16b486e27_2.png)

![](img/4aaa0601442398c4153434b16b486e27_3.png)

Okay， okay， so。So yeah， so this， this problem deals with a a couple of figures here。

 So figure1 shows a systolic processing element， right， And so figure1 figure1 is this guy here。

 And so this is one processing element。 And we're told that each processing element takes in two inputs。

 which are N and M。 And then it has two outputs， which are P and Q。

 And then every processing element also contains an accumulator called R。

 which is just like a data storage element。 And this can be read to and red from and written to。

 And the initial value the accumulator is 0， right。😊。

So figure 2 expands upon this and shows an array of these guys composed of 9 elements。

 And figure 2 is this one。So yeah。 So we have 9 of these processing elements here。

 And then these are gonna be input， input data tokens。So， okay， so we。

 we have that array of non processing elements。 And so we want to program this systolic array design to perform the following matrix multiplication。

 So we want the output C to be the matrix A times the matrix B， right。

 And so the matrix multiplication is， you know， just like row times the dot product of like row times column and then row times column to produce all the output elements。

😊，And so we have a bunch of like design specifications here。 And so in every single time cycle。

 every processing element， which is this guy down here， will take in the two inputs。

 perform a particular computation and then write the outputs。

 And the time cycle labels on the input boxes to determine which time cycle the inputs will be fed into the processing elements。

😊，And so that means that over here， 0，1，2，3，4 mean like these these data elements will be sent in here on cycle 0 and these on cycle 1 and these on cycle 2 and so forth。

 And same with these， these inputs coming this way， right。

So every processing element takes in those inputs and so any processing input element that is not driven will default to zero and any processing element that has no output arrow will also have its output ignored so the output from these guys is just basically discarded and any input that we don't actually specify is just going to be zero。

Okay， so after all the calculations are finished， each processing elements accumulator will hold one element of the final resultant matrix arranged in the correct order。

 right， So we want this output matrix， which is the 9 elements of C to basically be encoded in these guys。

 And we， we can assume that the correct order is basically the same order as the input。 And if sorry。

 the same order as stated here。 And if we assume something else， then we should。

 we should just say so。 So we're gonna go ahead and assume the same order for this case。

 So we want C 0，0 to be here， C 0，1， C 0，2， and so forth。😊，嗯。Okay， so yeah。

 we want that output at the end。So the question asks us。

 please describe the operations that every individual processing element performs using mathematical equations and the variables MN PQR。

 which are the input outputs and the register here so they give us empty fields for what should PV。

 what should QB and what should RB as a function of the inputs and R and so the second part asks us。

 please fill in all 30 input boxes so that the systolic array computes the correct matrix multiplication result described in the previous page and the hint says to you write it in terms of A。

 IJ and B， IJ。Okay， so I'm gonna leave the the matrix up here。 and then we have our。



![](img/4aaa0601442398c4153434b16b486e27_5.png)

Our our diagram here。It's okay。 it almost fits。 but yeah， so basically。

 we want to arrange all these inputs of A and B into these input boxes such that these computations performed correctly。

 right so。So， so suppose that because we want the outputs to be like this。

 we will take a look at the first the first output C 0，0。 So we know C 0。

0 should be composed of the dot product of this first row times this first column， right？

 And so we want a 0，0 times B 0，0 plus a 0，1 times B 0，1 plus a 0，2 times B 2，0， right。

 So we somehow need to feed those inputs into this box。

 So these A and B are gonna have to go either here or here and be fed into here 1 per cycle right。

 And so。For the next processing element， for example， C 01， C01 is over here。

 and so we're going to want this series of A's， but then the next column and so all the same A inputs need to go to this box and this box and also by the same logic this box so it would make sense to feed the A inputs this way right because those are going to be used by all three of these processing elements。

Likewise， for the B processing elements， we're going use them for c 0，0， C 1，0 and C 2，0。

 right because for C C 0，0， C 10 and C 2，0 will be the dot products of these rows times this particular column。

 So it would make sense to put them down here。 So now it's a question of how we want to arrange the logic such that the output operation will be correct。

So if we're passing the inputs from basically the same inputs are being passed to each of these three processing elements right in any direction we really think about。

 And so the same input element that comes in here， which is M is also going to be the output element P。

 So so these two are are identical。 you don't perform a transformation on the input for this particular output。

 And the same goes for n in  Q。 So if we're just passing the elements through。

 then when we come to our equations here， we're just saying p equals M because it's just a pass through and then Q equals N。

 and that's all that's going happen。And then in order to perform the dot product。

 every cycle that we have two of these elements come in。

 we're gonna to have to perform element times element and then accumulate the result。

 right because so every cycle we're gonna to get a new set of inputs。

 we're gonna multiply them and add them to the accumulator。

 So what we really want is R equals the original R plus the inputs， the product of the inputs。

 M times n。So this is， these are the operations that the processing elements will perform individually。

 And so the last part of this question is to kind of figure out how to organize the data such that we we get this computation performed correctly。

So， okay， so we can think about this in terms of at what cycle the inputs will reach particular elements。

 So for this first element， in the initial the very first cycle we'll have data to compute with。

 So we want to put the first elements we can here。 And so we can put elements here in here and the cycle after and the cycle after。

 And since there's only three， we want to do， we can just leave nothing in the outer two cycles。

 right， So we can just have zero inputs here because we don't need to do anything。For this guy。

It will receive an input on the very first cycle here。

 but it will take two cycles to receive an input here。

 right So we don't want to put a data element here because otherwise。

 we'll just have one input and then nothing here。So instead。

 we're gonna pass the input from the second cycle that way。

 when this one reaches this processing element， this one will also reach this processing element and will' perform the correct product。

 So we we're gonna have zero。 And then by the same token here， it's gonna take two cycles like 1，2。

3 to get here。 And so we want this data to also take3 to get here。 So we're gonna have data here。

 meaning that these two will be zeros。 And so by the same logic over here it's gonna take two cycles to get here。

 So we want this data element to come at the same time as this one。

 So we're gonna put zero here and also here。 So so now we know we want to arrange our data。

 basically in this fashion。😊，And then this fashion over here。

 And so we just have to add these inputs， right， So on the very first cycle。

 we can have this guy compute a 0，0， and then B0，0。And then on the second one， we can have it do A 0。

1。 And then over here， we can have it do B1，0， and then so forth。Sorry， oh， is it off the edge。

Oh yeah， okay。 So， so yeah。 So at this point， we've， we're basically done with the problem。

 We're just filling in this table in terms of like what， what cycle the inputs get here， right。

 So a 0，0， a 0，1， a 0，2。And then here， B2，0。 And for this guy， he's going to be computing the。

 the product of the first row， which comes in。I guess I got A And B backwards。Yes。Very good。 Yeah。

 yeah。 So， okay， so I'm gonna write this again。So this is a 0，0。 this is a 0，1。 this is a02。

 and this is B0，0， B1，0， B20。 Okay， yeah， so this guy's gonna take in the three A's afterwards and we're gonna require the second column of B's here。

 So this is gonna be B0，1， B1，1 and B21 and then so on and so forth。

 we're just fill in the table yeah。Okay， so so yeah， that's both parts of this question。

 And if you just fill in the rest of this。 So any any， any questions about this one。

 I think it's a lot more straightforward than some of the other ones， so。Yeah， okay。 yeah。 Yeah。

 I guess we have a solution sheet。 So there you go。 It's， it's， it's done。

So this this is like typical question in which you have to calculate what's the CD utilization。

 remember that the C utilization not only in GPUs but also in vector processors meaning like the ratio of lanes that you are actually using So here the first thing that you have is the definition C utilization of a program run on a GPU is defined as the fraction of CD lanes that are kept beat BC with active threads when are we going to have active threads well we're going to have active threads when we actually execute some instructions for these threads the question give us some piece of code and this is essentially a for loop as you can see。

And it says that this is going to be executed on a GPU。

 so the way that this is going to be executed on the GPU is distributed in the iterations of this loop across the threads that we have in warps so here we have N iterations and these n iterations are going to be executed by a certain number of。

Warbs， that's the first question。 That's part A。 How many wars does it take to execute this program。

 Please leave the answer in terms of N。 So we have。Any iterations。We know that the warp size is 32。

 a warp in the GPU consists of 32 lanes and we also have sorry 32 threads and we also have 32 cdy lanes in the GPU n divided by 32 is the number of wharves because so in case that n is not divisible by 32 we have to use the ceiling of this division right maybe the last warp is not completely busy but we will still this number of whs。

Part v， assume integral arrays a。So we have A And B。 A has a repetitive pattern with 24 ones。

So it will be something like these， 24 ones。Followed by。8 zeros。

And B have different repetitive patterns， which have 48 zeros followed by 64 ones。

What's the c utilization of this program。 So observe that this is the repetitive pattern of a and a。

The values of a determining if the body of this， if a statement is executed or not。

 As you already know， this， if a statement will be converted in some into some kind of。

Comparison and some kind of branch， right， Because in case that you don't need to execute this body。

 you will have to branch in order to avoid these。L body。

 So that's why depending on what's the exact value that each of the 32 threads of the war of the warp read。

We will execute the body of this if a statement or not， and observe that here。

 the condition is that a is divisible by three。Because all these 24 ones that we have here are not divisible by three。

Only those。Threats that read a。I equal0 will actually execute this statement here。So。

If we have two instructions， instruction 1 and instruction2。

 the first instruction for sure is executed by 302 threads， but the second in each warp right。

 but the second instruction instruction 2 is only executed by those threads for which a modular 3 is equal 0。

 that is for this a threads that read these a0s here。So。Outdo。

32 plus 32 that would be the maximum number of threads that we have executed this instruction one and then instruction two threads that belong to the same world。

呃。They seem the。Utilization in this case， is 32 plus 8 divided by 32 plus 32。So， this is。40。

Divided by 64。So that's the answer to this part B。second part is。

 is it possible for this program to j CM utilization of 100%？Well， and the answer。Is， yes， But this。

 this case in which the same utilization is 100% is going to be。

Depenent on the value of each of the elements of register， of array， A， As you already know。

 there are two possibilities here。If we want to have 00 percent in the utilization。

 the first possibility is that。All threads in each warp。Execute instruction one。

 and then they go into the body of the E statement and they execute instruction 2。

 That's one possibility。 The other possibility is that the threats in the war。

🎼All the threats in the war execute instruction  one， but they don't execute instruction 2。

 because this if condition is not true for any of them。 So the answer in this part。 If yes。

 what should be true about our race a for scene utilization to be 100%。

 The answer here is two possibilities。 every。🎼32 elements。Es。Disible by three。Or every 32 elements。

呃呃。Athan。Disible by three。So either way， we will have all threads in the warp executing both instructions or only executing one of the instructions we are going to stop here because were run out of time the rest of the exercise is very similar you already know how you have to reason about this exercise here there is a question part D and E are very similar questions but the percentage。

 the S utilization is different you can reason in a similar way and the very last part is actually quite easy。

 this is what we explain in the GPU the first GPU lecture about dynamic warp formation。

 you might remember that there might be a way of， let's say。

 merging warps like this where some threads are active other threads are not active and if these threads that are active are not。

In different words are not in the same lane， they can be merged and this way we can have more efficiency in our execution。



![](img/4aaa0601442398c4153434b16b486e27_7.png)

We stop here。Okay， this question is about vector processing。

 So we have assume a vector processor that implements the following IA。

We have set instructions to set vector to register and vector lens register。

 We have loads that loads。From memory into a vector register。This takes 100 cycles on its pipeline。

1000 cycles per。 So if we have a back total length of 100， we will have 100。ELatency per load。

 but they are pipeing。 We can initialize one per cycle。The same for the stores。

 you have 100 latency pipeline。诶。Multipies  ten0 cycles up five cycles divide 20 cycles。

 all of them pipeline。So。Just soon the following processor has an in order pipeline。

 the size of the a vector is4 bytes。The size of the vector side register and vector length register is 10 bits。

The processor does not support chain between vector functional units。 The main memory has a bangs。

EAmbmbor elements are restoring consecutive。Memory addresses。

 vector elements that con with the memory address are interleave between the memory ones。

 So if a vector element address a。Maps to rank P about the next address。

 a plus4 address to the next bank。And， the number of functionsk is not necessarily a power of two。

So the memory is wide addressable。Bector El is her story in a four vital aligned manner。

 Each memory bank has 4K row buffer。 I think this information is not required for this exercise。

Each memory angle has a single width and single right port so that a load and store operation can be performed s simultaneously。

 And there are separate functional units for executing load and stores。So what should be the minimum。

What should be。The minimum value。Of an to avoid stalls while executing low sun stores。

 assuming a better of strike of one。So the latency of accessing one single one is 100 cycles。

 So standard cycles。And we can。So one bank will be occupied for 100 cycle。

So if we pilot blank these operations， we can access the N bank Str  one。 So this is bank 0， bank1。

 which this will take 100 cycles and so on so。 So we can。Access this bank again after 100 cycles。

 So to not installing the the loads， we need 100 banks。 So 100 banks。

 we access one of them each cycle。 So in the cycle 100。诶。We will access the， the， the last bank。

 And in the next cycle， the first bank will be already done with the with the first load。

 So with 100 banks。Is enough to stall any to avoid any stall in those stores。

 Notice that if you have， for example， a load a vector length smaller than than 100。

We could have less banks as well without the installing。 But here is his。He。

So we have to assume that the vector length can be any length。 So in the worst case， is 10 bit。

 as we saw here。 So it can be more than 1000。Yeah。Bector length。

 so we have to assume that in the worst days。 So 100 is the correct answer。对。一审个。かてれ。Yeah。

 they are two different memory banks。 Yeah， so it's specified here， right。

 vector elements is story consecutive memory。 others are interve between memory banks。

So the next question is， what should be the minimum value of of banks。

To avoid these stalllls while executing load， load or restore， assuming a strike of two。

So we are assuming the straight of two。If this is10， bank1。帮 two。So if we assume a straight of two。

 the first access will be to bank1。 The second axis will be to bank 2 and so and so on。

 You have 100 banks， as previously。The， the access number 50 will be accessing this bank that will be occupied because this takes 100 cycles。

 right。So，100 bank is not enough。For high for not installing the load instructions。

But if you have an extra。诶。An extra bank。 you have 100 and1 banks。 What will happen is that。Is that。

Is that we access。 So in the in the second， let's say in the second iteration。

 we will instead of accessing this one， we will access this one。So we will。

 we will be filling the gaps in the second round。Let's say。With 100。Angu banks。Yes。Explain by 70。去。

Can you repeat that， yes。Can we also say the greatest common device？101 and2。The number of banks。lot。

Yes。Yeah， yeah， yeah， yeah。Yes。As far as a reasonable。Answer is， okay。So O。Next question is。

As soon a machine that has maybe as many rank as you found in part A。 So n is 100。

The vector stride is one， and the value of the vector length is set to M。 but we don't know M。

 we don't know the band vector length。So and， and the machine secures this code。

So the total number of cycles needs to complete execution is， is this number。What is him， so。We can。

 let's say， draw。诶。This code。 So the first load， it will take。呃。100 plus n-1。Is clear why。

Why is this the latency。Have to splennd this。 This is because。So。If we have。呃。So。If this is one。

 so we can start one new。Lothe every cycle， right。 So at the end， we will have。We will have this 100。

Because if this the latency plus this latency that this latency is the pre So if the total one is M。

We have 100 for the last one， and then we have n-1 here cycles。

 we can start one load every single cycle。 So we have。呃。So yeah。

 this is the latency for for the load。 So the next load。You can start the next load。

After the first load， it takes the same。latency。嗯。靓。Dad。So， the art depends on。你变送B1。So only is。

 it is independent of V2， so we can start。The add here。

 But as we can notice start two instructions in the same cycle。

 we need to wait for one instruction here。 so we， we will。呃。We require one cycle here。

 plus five cycles， plus and-1。Okay， next is the multiplication。嗯。This depends on。B 2，1， B3。诶。

This depends on the a。In the load so we can so。 And the last one to finish is the load， right。

 so we can start。The multiplication here。嗯。That is multiplication is。T cycles。Plus， M well。

And the last is the store。That depends on before。 so we can start after。

After a multiplication and the story is。1 hundred0 cycles。Plus n-1。So to know the latency。

 So we have the latency of this part。 So iss 100 plus。And-1。

So this late intensityt is hidden because this is larger。 So we have plus 100 plus and minus-1。Then。

 well go here。意。Bing。Theres one。Plus100。And minus。Plus-1 equal to。To this latency。

And if you solve this equation。Yeah， M is 1000。Questions， yes。Instruct is finishing this。然后还在。

身份 back。Finishes much sooner than the vector。Mhmm。😊，印花的。do we assume that we have。For the second。

这个月使用的。Both assumptions are。Prisonal right。So。也。More questions about this one。So。

 and the last one is。So if we might find later professor to support training。

 So now we support training。So呃。Again， it's the same code， right， So we have the load first。

We have 100。Last。嗯。N-1。So。诶。AndWe have the second load。

Second load is independent from the previous one， but we have only one load execution unit。So。

 we have 100。Plus n-1。Yeah， they are。On the。Where is the。手啲啊。And depends on B1。Depends on this。

So because the processor is in order so we can only start the ad after。After this load。

 so we can start again one cycle after this load。 So we have。5。And 나の 소。Ds instruction。Is the mor。嗯。

The multiplication depends on B2 and B3。So， we to。So depends on the a and depends on these two instructions。

But we can start because we have chain now。We can start executing once we have the first element of。

 of， of the of the two vectors available， right， This is at this point。So when we load。

 we have the first element of the load after 100 cycles here。 So we will have this before。

 So at this point， we have already available the first element of of of the vector。

 So we kind start the the multiplication here because now we have chain。嗯。

So we can start the multiplication here that these tiny cycles。Plusus and-1。嗯。D store。The store。

Depends on before that is the multiplication。 the result on theplication。

 So we can start the store after the first element of the multi of the。

Vctor multiplication is is calculated so we can start the store here。 This will be。100 cycles。

Last m-1。So on if we。Formte this equation。嗯。We have。So M， M is the M is the value from the pres。

Previous questions， only is 1000。So we have the la here is。诶。So， this one。Plus。Plus， this one。100。

Plus。10 plus n-1。Oh， no， sorry。Plus 10 plus 100。Plus， n -1。Equal to number of cycles。

 and Institute N。For。1000， the results should be。Should be。Should be this。do something。😔，Yeah。



![](img/4aaa0601442398c4153434b16b486e27_9.png)

Any questions。We define the CD utilization of a program that runs on a GPU as a fraction of CD lanes that are kept BC with active threats during the rung of a program of the program。

 as we saw in lecture and practice exercises， the S utilization of a program is computed across the complete run of the program。



![](img/4aaa0601442398c4153434b16b486e27_11.png)

The following code segment is run on a GPU， each thread executes a single iteration of the shown loop。

 assume that the data values of the eraser A and B are already in vector registers so there are no load and stores in this program hint notice that there are three instructions in each iteration there are clearly marked here in the code。

嗯。A warp in the GPU consists of 32 threads， and there are 32 Sim lanes in the GPU。

So we have warps of 32 threads。 That's the warp size in this case。

 and the total number of iterations that we have is 1025。

 So the way that we need to calculate the number of warps is by obtaining the ceiling of the division 1025 divided by 32。

 and this will give us 3333 warps okay the only important thing to keep in mind here in this part of the of the exercise and also in the in the rest of the exercise is that warp number 32 assuming that we start number in the warps from warp 0 in warp number 32 there is only one single。

Threat active。That's important for the rest of the， of the exercise。For example here， in part B。

 it says， what's the maximum possible C utilization of this program。

 hint the warp scheduler does not issue instructions when no threats are active。

 This is something that we discussed when we studied CD processors， we talk about。嗯。

What was that day。嗯。嗯。Density time implementation， I think what's the was was the name when we。

 when we somehow do a scan operation throughout the mask to make sure that there are at least some threats active before we actually issue the instruction。

 So in this case， we the scheduler checks if there is if there is an active thread， there is no。

 if there is no active threats， then the instruction is not issued。 So in this case。

 how can we get the maximum possible C utilization。

 maximum possible C utilization will be the case where all threads in a warp go through the same path。

So， notice that。The first instruction here， instruction number one， which is this if statement。

 is going to be executed by all the 1025 warps threads right。

 So there is no possible divergence there。 We are going to have， let's say。

100 percent utilization for this instruction always。

 But then there is a possibility that the threads within the same warp diveerge。

 and part of the threads go and execute instruction 2 another part of the threads go and execute instruction 3。

 This is not the case that we want to consider， right。

 the case that we want to consider is where there is no divergence in this case。

 we will have maximum utilization。So the way that or the maximum utilization that we can actually have in this program is going to be 1025 divided 1056。

 Why is that Because we only have 1025 threads active out of 1056 threads that exist in 33 warps。

 So it's impossible to have 100 percent utilization in this program for the single reason。

That we the last warp is not complete。 So that's why we get this number。And now the question is。

 what should be true in this array A for this maximum utilization to happen。 That's what。Part。C asks。

 please describe what needs to be true about array A to reach the maximum possible C D utilization ask in part B。

And it says please cover all cases in your answer。 Ober that whatever the answer is。

 we will have to give the answer at warp granularity。

 Why is that because the instructions are issued at warp granular granularity。

 So divergence is only a problem within a warp， there is no， let's say。

 divergence there is no problem in terms of utilization If the threats of one warp go and execute instruction to and threats of other warp go and execute instruction3。

 So the right answer here is。4our。Every。32 threads。They all will go。

And execute instruction 2 or instruction 3。 So which means for for every 32 threads， consecutive。

32 threads， we will have 32 consecutive。Values of。A。We are。Lower than 33 or。Greater or equal。2 33。

That's the answer。And that's what needs to be true for this array A in order to have maximum utilization in this program。

Is it dear。最一的。If you if you know no， no， no that that might not be correct。

 So if you have found that in some question in the optional homework。

 please put the question in model and and we will look at it maybe in some of the cases cases。

 what you might have seen is that instead of 32 is 64 because in some cases we say that the warp size is 60 64。

 but this is just the way it's defined in in the beginning of the exercise。The。

 the entire array that that might be wrong。 But just to make sure， please put the。

 the question in Mo。Okay， next thing is next part is part D。

 what's the minimum possible C utilization of this program。So how can we。

 how can we obtain the minimum possible utilization of this program？ Well。

 we already know that this instruction  one is always going to be executed by all threats。

 So we are always going to have hundred percent or 1025 divided 1056 utilization for this instruction。

 And then what we need is that within each。Wp， we have divergence。

 So some of the threats of the warp will execute instruction 2。

 while others will execute instruction 3。And let's say， I don't know。

 the number actually can might change from word to word。 But， but let's assume， because actually。

 this doesn't affect the answer that in every。Wp。Alpha threats。Execute。Instruction 2。And the rest。

32 minus alpha。Go and execute instruction 3。So by taking this into account the way that we can calculate the same utilization is by going instruction by instruction and war by warp。

 Im thinking what is happening there for the first instruction， we already know that 1025 threads。

We'll execute instruction 1 out of 1056。And then we have instruction 2。

 and we know that alpha threads in each warp will execute it。 We have。32 complete wars。

 I'm talking only about the complete wars。 We will talk about the last war with one single thread active at the end。

And this is。Out of 1000。24， which is 32 times 32。And then instruction 3 is executed by 32 minus alpha times 32。

Threats， and we divide by 1024。 And then we have the last。W。

We don't care if this last thread executes instruction 2 or instruction 3。

 The result is not going to change， but it's only one thread， every。

32 threads that belong to the same warp。So， these。As you can calculate yourself， will be。1025。

 divided by。1568。And that's the minimum seemed utilization in this program。The next part。

 part E asks， please describe what needs to be true about array A to reach the minimum possible S utilization ask in part D。

 So what we need to make sure is that there is divergence within each warp。 So what we need for。

Every。32。Consecutive。Elements of a。We need。Part。Of them。B。嗯。Lower than 32， and。The other part。B。

So sorry， I said 32 is 33 and the other part be greater or equal to 33。O。

For every 32 consecutive elements， such that we make sure that we have divergence within each warp。

And then， for the last part。F， what's the in utilization of this program。

 a program where AI is equal to I。A经。For instruction one。

 no matter what's the what are the characteristics or or what's true for array A for instruction1。

 we will always have 1025 divided 1056。And then we have that instruction， too， is executed by。

33 threats。 Why is that， Because this condition here。

 the E statement is only going to be true for threats with。A threat， I D。Lower than 33。

 So there are 33 threads that will execute instruction to。 and notice that this is。The entire warf 0。

Composed by 32 threads。Plus。One thread in。W one。And then the rest of threats will execute I， I 3。

 including the threat in the last warp。So， we calculate。In the same way as we did before。1025，1056。

Plus。32 plus  one。This 32 corresponds to Warp 0。 This one corresponds to the first threat of warp1。

Divided 32 plus 32。 And then we have。960 threads that go all。And execute instruction 3。960。

 And then we have the last warp。With one single thread out of 32。And this will give us。

1025 divided1072 right。So whats special about this。来。呃嗯。性な。AndBecause the link。Yes。Fing。

In this case theyYes。Well， that's assuming that there is dynamic war forming。This， this， this。

 this doesn't hold here we。Because so this is somehow it and actually the way it was explained was like an optimization。

 possible optimization for web scheduling on GPUus if this is not something that real GPUs implement by default。

And actually， I don't know about any GPU that implements that。 real GPU and。If we， you know。

 decide to。I mean， it will be possible that we have an， a question like that。

 but we would explicitly state that case。ま今さササズ。じゃなで。In this， like a tri logic。case。No。

 you shouldn't。 You shouldn't make that assumption unless it's clearly stated in the question。

So for the， so the reasons are， I think it's the second exercise of this type that I solve here and this this year。

 and I didn't consider that in in any of both cases。 and actually。

 if you read the questions that we have in the optional homework。

That that dynamic war formation is is not there。 I think， yeah， maybe in in some exam。

 we some time ago， we， we asked something like that。

 but it was clearly stated now considered that there is dynamic war formation。DYes， so by default。

 as I said， dynamic word formation doesn't exist。 So you shouldn't consider it。 I mean， if you。

 if someone has a question in the exam， it's the one thing that you can always ask。我的。here because。

I mean， you should be clear for now on， right。And because I告 them。And they。like there was a。

 I don't know much second process。And it wasn't say that we used pipeing or not。对这边。在。So then at HDD。

 it was clear。だグです。把这份诉的。で。拍だな。Well， I mean。对把这个。I meanYou're 400 students， you know。

And we are only 60 days， so。The， the variability of assumptions is is larger in your case than in your case。

 And these things might happen。 But that's why it's good to us anyway， about the multie matching。

 I can， the only thing that I can tell you is that multie matching the way that is explained in this course is never pipeline。

😊，下面的处。Okay， but yeah， feel free， feel free to ask everything that is not clear。

 And maybe one recommendation is， is also before starting to solve one question。

 read it completely because maybe， I mean， you you， you see how the questions are written， right。

 maybe they are very long in the beginning。 but then you know that different parts， it's。

 it's very short。 So if you read the beginning， then you're not going to spend more than a few more minutes to read everything。

I assumption I would。M okay。该成一。我认好。The same single。Yeah， so that， that would be， I mean， if。

 if we tell you， now assume dynamic word formation in the way it was explained in the lecture。

 then you will need to worry about the fact that they are in the same lane or not。

 but maybe another possibility could be lanes can migrate。But in principle， don't worry about that。

Anything else。OK。It says we define the CD utilization of a program run on a GPU as a fraction of CD lanes that are kept busy with active threats during the rung of a program。

The following code segment is run on a GPU H thread executes a single iteration of the shown loop。

 assume that the data values of the arrays A V and C are already in vector registers so you don't need to worry about memory accesses and it give us one hi there are six instructions in each thread I will tell you now how to count these six instructions our warp in the GPU consists of 64 threads where there are 64 C lanes in the GPU。

And there are 64 single lane in the GPU。 So the six instructions are。This。Is the first one， this if。

Then we have three instructions inside the first if statement。

 then fifth instruction is second if and this is the sixth right why don't we have to worry about the for loop because in the end the for loop what is simply expressing is the number of threads that we need to use This is like the sequential code that we are going to paralyze using the multiple threads that the GPU provides right and what the question also says is that each of the iterations is going to be assigned to one individual thread So we already know what's the total number of threads that we need to execute this program right is 4096 okay。

And this takes us to the first question part A， how many wars does it take to execute this program。

 how many wars do we need to execute this program？So， the number of wars。Is the number of threads。

 which is exactly the same as the number of iterations divided by the size of the warp， which is 64。

And this is。64 ws。This is the number of warps that we need to execute this program。

 the number of warps of 32 threads each， because in this particular architecture， the warp has 3 60。

 sorry， 64 threads in another different problem you can find 32。

 but in the end there won't be any difference。Okay， so these are 10 points for free， as you can see。

Second part is more interesting。 It says when we measure the symptom utilization of this program with one input set。

 we find that it is 134 over 320。 What can you say about the race A， B and C， be precise。

 look at the if branch。 So look at the if branch means。

You have to analyze your code and see what's the influence that the different arrays have on the execution of this program and the utilization of this program and as you can see。

 the only important thing to keep in mind with respect to that is are they if statements right and in the statements。

 the only thing that we have is B。So actually， A and C don't have any effect or any influence on what's going to be the actual path of execution。

So， simply。We can say， what can we say， We can say nothing。About a， And we can say。Nothing about sea。

But about B， we can say many things， right。And why is that because depending on what's the particular value of V。

 each thread will go through this if statement or this if or none of them。

Why is that Because there are three possible values that are important in for B， I 8，8，8，8。Which is。

 we don't execute anything。 None of the， of the two paths or greater than or less than， right？

 So these are the。3 possibilities that we have for the values of B。But now the thing is。

 how do we reason about what's the actual utilization， which here is 134 divided by 320。

So what I would recommend you and let me use this as a scratchpa。

 what I would recommend you is that you first start looking at what's the total number of instructions that the program has。

 And we know that the program has six instructions right How can we calculate the utilization。

 let's say in a generic way， when we have six instructions。

 So what we know for sure is that this six instructions， are going to be executed。

 potentially maybe not。 but they are going to obviously depending on whats the actual path of execution。

 but they are going to be executed by 64 wars of 64 threads。And there are some instructions。

 And you can see here。That are always executed by every threat， in particular， this one。And this one。

 Why is that， Because we have to evaluate the EA statement， right？

 So this is something that I can already include in the numerator。 I know that。

All the threats of all the wars are going to execute the first。This is the first。E。And。The second if。

O。And what about the other instructions， The other instructions are these three。And this one。

We don't know that， right。 We don't know how many threads are actually executing these three instructions。

 but it is likely that not all the threads inside the same warp execute the same instructions， right。

 So let's assume that there is a number of threads。Es in each warp。

That executes these three instructions。And there is also a number of threats， why。嗯，应。

Every warp that executes that sixth instruction， this is。Why is not for。To make sure。O。

And what the question says is that this is equal to。134， divided by 3，20。

And now we have to think a little bit about the numbers that we have on the paper。

If you look at these。So if you look at this expression here。We can get rid of。All these。64， right。

 That's super easy。 That's clear。And now， if we look at the denominator。

 we will see that this is equal to 384。And 384 is not equal to 320。Right。Actually，320。

Is equal to 5 times 64。Which means。That in this particular case。

 only five instructions are executed by any threat。If we go back to our code。

The only possible way that this happens。 Only5 instructions is that no one executes。This instruction。

And this way， we will have this one for sure， this one for sure。 and these three。How many threats？

 I don't know that。But I know that this number is e。Oh， sorry。Okay。

 the number of threads that execute these three。 So what I need to do here is to somehow。

Rewrite this expression for only five instructions。 This is 64 times 3 plus64 times 64， divided by 5。

64，164。 And again。I get rid of these 64， and。This is equal to。This。And from here。

You will find that E。Is he got to。Okay。So。Right answer here is that。2。Every 64。Elements。off。B。A。类似的。

Does it make sense。You can check it yourself。 There is no other possible answer in this particular question when we when we prepared these kind of questions。

 we usually try that there is only one single possible answer I'm pretty sure that you can come with other numbers that can take you to different combinations of x and y。

 but this doesn't happen in this case。 So what as a general recommendation。

 what you have to do is to look at the numbers that you have in front of you and reason in that way because the numbers are usually pretty simple it shouldn't be difficult for you to reason in this way。

Okay。Okay， part C， is it possible for this program to gel a in the utilization of 100%。

 And the answer is yes。And why is that。Because we so what it says what should be true about A。

 B and C for this to happen again， we don't care about A and C。 We care about B。

 same as in the in the previous part。 And if you want to have 100 percent utilization， essentially。

 what you need is that all the 64 threads of a warp， which go through the same path。 I mean。

 all the 64 threads of a warp always go through the same path。 And for that。

 there are three possibilities。 Indeed。 and the three possibilities are。That they。

 that every 64 elements of V are equal to 8888 or are greater or are lower than。Right。Every 64。

Elements， so maybe the first 64 elements are equal to 8888。

 and the next 64 are greater and the and the next 64，64 are lower。Is it clear。Okay。Every 64。Elements。

Will be equal。Or these。Or that。Okay， and then last part。Part D， here it is。

 What is the lowest seemed utilization that this program can yield。

And this is actually very easy to answer。 Of course， you need to calculate the the number。

 but it's very related to to what what what we already discussed in in part B。

 right because in the end， in part B discovered that there were two threads in every war that are executing the same path right and and this means that you have two threats。

 So if you want to decrease the utilization instead of to use one right， And so this this way I mean。

 the way to to achieve the lowest utilization is to have one single thread。

Going through this path and one single thread going through this path。And here you could calculate。

Something like so the the way to calculate the actual number。Would be 6 times 64 times 64。And here。

 one times。64 times 3， which is the number of instructions in the first eve。And then。

64 times 64 plus。One times64 times one， which is the number of instructions in the in the in the second eve right and the value that you will find here is 132 divided by 3。

84， right。You also need to explain。 But， you know， the explanation right， is one thread is greater。

 One thread is lower， and the rest are equal。Right。

But do not forget to explain what you're doing and why are you reaching to some particular result。

Any question。So we have a question about tracing the cache。

 So we spend a little bit of time looking at caches。

 And so this goes over some like some of the more fundamental concepts of caching， right。

 So in this problem， we're saying that we have three types of CPUs。 We have the 68，0，8 D T and F。

 okay， and all three of these CPUs feature one level of caching。

 So the system looks sort of like we have a CPU here。 And then we have an interface to a cache。😊。

And then， the cache interfaces with memory。And so each one of these CPUs has a different type of cache。

 right， And so we're given that the cache size is 128 B and the cache block size is 32 B。

 So that tells us that precisely four blocks fit in one of the caches， right。

 And we also know that the cache uses the least recently used replacement policy。

So the only difference between these three caches is the associivity。

 So we're given that D uses a direct mapped cache。 T uses a two way associ of cache。

 and F uses a fully associative cache。 So if we go ahead and draw these out。

 then we're saying that D is a direct mapped cache。 So every single block it gets its own set， right。

 So we have four different sets in the cache。 and there's only one way。😊。

Numbered the design T uses a two way set associ of cache。

 So we know that there's two sets and two ways because there's precisely four blocks in this cache。

 And then cache F has a fully associative cache。 So there's only one set。

 which contains all four blocks。RightSo when when each of these caches store a block in D。

 it's mapped directly to only one set with T， it's mapped to one of these sets。

 but it could go in either way。 And with F， all blocks are going be mapped to this one set。

 but they could occupy any of these ways。 So we have these three caches。

So then we're told that we run this particular program。To evaluate the CPUs。

 And this benchmark tests only memory read performance by just issuing a series of reads to the caches。

 And so we're gonna assume that the caches are empty before we run the program。 Okay。

 so the cache accesses that are generated by the program are as follows in order of access from left to right。

 So we have a sequence of accesses to the bunch of different blocks。

 So this is these are accesses to the cache by the program。

 So there what they're what's going on on this bus。😊。

So every single letter here represents a unique cash blog。

And all eight blocks are guaranteed to be contiguous in memory。 However。

 the ordering of the letters does not necessarily correspond to the ordering of the blocks。 So it's。

 it's a mystery for us to solve。 We don't know how these fit together。

And for then we're given that for the Dc， the direct map cache。

 we observe the following sequence of cash misses in order of generation。

 And so the cache misses are when the CPU requests from the cache。

 but the data does not exist in the cache。 And so the cache has to go out to memory to get the data。

 So the misses are what's going on on this bus。And so by using these above traces。

 we want to figure out which cache blocks mapped the same set for the 68，0，8 D processor。

And so we can say a couple of things right off the bat。

 So we have 8 cache blocks that are contiguous in memory。

 but we only have four locations in the direct map cache。

 And so by looking at some of the bits in the address。These。

 these cache blocks will be mapped into precisely one of these four sets， right。

 So given 8 fitting into4， we're gonna have two cache blocks mapping to each set。

 And so we're basically looking for pairs of cash blocks that belong to each set。

So we have the sequence of axes， and we have the sequence of misses。

 so we can begin taking a look at how to go through this。So let's。

 let let's draw out an empty cache here。So this is what our cache is going to look like at the beginning of the program with nothing in it。

 And these represent the four different sets。 So at the beginning of execution， we have。

This sequence of aes， which starts with a。 and we have this sequence of misses。 And so so a。

 so when the program first requests a， it doesn't exist in the cache And so we generate a miss。

 which makes sense because it wasn't in the cache previously and we don't know where it belongs in which order。

 but we know that it's gonna to be in one of the sets。 So we just assign a location。

 So this a generated this miss。 Then we have B and B also generates a miss because it hasn't been seen in the cache yet。

 but we we don't know where it goes because it could be in the same set as a or it could be in a different set。

 So we're gonna leave it alone for now。 Then the program requests a again。

 And a appears to generate a miss。 And so this means that a was kicked out of the cache when B was brought in because B has been the only thing in between。

 And so that tells us that A and B have to belong to the same set。 because when B was brought in。

 A was kicked out。 And then a comes back in and a generates another miss。

 So this sequence of misses comes from these guys。Then we bring in H。

 and H generates a mis because it's not in the cache yet。

 And so we can arbitrarily assign that a location。Note that you can't put H here， right。

 because we already said that there can only be two cache blocks per set because these blocks are contiguous in memory。

So then we bring in B， and B appears to generate a miss。

 which makes sense because A was the last thing that was brought in。Then we bring in G。

 and G generates a miss， which again makes sense because it's not in the cache。

 but it's the same problem。 we don't know where to put it。 So we're gonna to leave it alone for now。

 Then we bring in H。 sorry， we don't bring in H， but we try and access H。

 And H does not generate a miss。 So that means H is already in the cache。 And when we brought in G。

 it did not kick out H。 So G has to belong to a different cache set。Otherwise。

 H would have been kicked out and would have generated another miss。So G is responsible for this。

 H and H are both already in the cache， so there're just hits in the cache。Then we bring in A。

 and A generates a myth， which is true because B B B was brought in previously to kick it out。

 So then we have E。 And so E generates a miss because we haven't seen it。

 but we don't know where it belongs。Then we call H。 we we try and access H。

 and H does not generate a miss。 The next miss is actually D。 So H is still in the cache。

 So we know that E must go either here or here， but we're not sure which yet。

Then we access D and D generates the miss， so。So yeah， DD has not been seen in the cache。

 so we're not really sure where it goes either。H， H is an X access。 and it generates a miss。

 So we know something kicked out H。 But the thing that kicked out H could not have been E because we've already shown that E cannot belong E cannot belong to the same set。

 So that means that this， this cache miss from D had to have kicked out H。

 Otherwise H would not have needed bringing back in。 So D has to be there。

Then we we try and access G。 but G does not generate a miss。

 And so that automatically tells us that G is still in the cache。 And so E has to belong here。

 And so G is a hit。 Then we have C and C generates C does generate a miss。

 And so C has previously not been seen in the cache。 So we we also don't know where it goes。

 Then we have another axis to C， which is a hit because it's already there。 And then we bring in G。

 And we see that G is a miss。 So G has been evicted in the past。

 And the only thing it could have been evicted by is C。 So G has to belong with C。 And finally。

 the only thing that we have left is F。 So at this point。

 we know which which addresses which which cache blocks belong to the same set And so this is our solution。

 So we can say A and B belong together H and D belong together G and then C and then E and F。Right。

 so we've， we've solved Part A at this point。 Are there questions about this part。Before we like。

 me move want the next one。Okay， so part B asks us to write down the sequence of cash misses for the F processor in order of generation。

 And so F is our fully associative processor。 And fully associative cash。

 And so we know that in the fully associative cash。

 every single one of these cash blocks will map to just the only set there is。

 but it can occupy any of these positions。 And we are also told that the cash uses an L RU replacement policy。

 right， So we know which ones get evicted when， when an eviction occurs。So， look another paper， okay。

So we're gonna go ahead and trace out these cash misses in their order of generation， right。

 And so we're basically just gonna to enumerate how all this happens。

 So we're gonna draw a sort of just a model of what this， what's currently in the cache。

 And so we have one。 we have one set， which contains four different ways。

 And we know the sequence of aes that occur because it's given to us。

 And so we're just gonna go ahead and go through one by one and simulate what's happening in the cache as we go。

So if we， I'm just gonna transcribe the sequence really quick。 So we have。Just copying this down。

Yeah， so thiss probably enough to get going。 So this is the sequence of program Aes。

 And so we can just begin simulating this cache。 So the first A is gets brought into the cache。

 And so it's a miss。 So I'm gonna to denote that by putting an X underneath it。B gets brought in。

 It's also a miss because it doesn't exist in the cache。

 But we put it in a different way because there's free space。 So that's a miss。

A is a hit in the cache because it already exists here， so that's fine。H is new。

 so we put it here and mark it as a miss。B is already in the cache。 So that's fine。

 G is not in the cache。 So we bring it in， and it's a miss。H is already in the cache。

 already in the cache， already in the cache。 So this is a more interesting one。 So we have E。

 which is not in the cache right now。 So it's gonna to be a miss。

 but we have to figure out where in this like what gets evicted in the cache。

 And so this is where the replacement policy comes in。

 So least recently used means we're looking for the the cash line that hasn't been accessed。

 the oldest cash line essentially。And so we can basically look backwards to see what's the oldest one that's currently in the cache。

 And since everything is kept in the cache up until now， we， we look at a。

 which So so A is in the cache。 H G， these three are all in the cache。

 and they've been recently accessed and。The least recently accessed one ends up being B。

 because it's the farthest。 And so B gets evicted。And instead， we put in E。 So E is now in the cache。

Then we have an access to H， which is a hit。And then we have D， which is not in the cache。 So， again。

 we have to choose something to evict。 And based on the L R U policy， it's going to be not H， not E。

 not A， but G。 So G gets evicted， and we replace it with D。And so that's a myth。

Then H is still in the cache。 G is no longer in the cache because we just evicted it。

 So now we have to pick what's evicked next。 So the least recently used again， not H， not D， not E。

 but A。 So A gets evicted， and we replace it with G。And she is a myth。C， so， so yeah， basically。

 you just repeat this process for the the whole set， for the whole set of aes that we have。

 And you write these down in order here。And that that's basically the solution for Part B。

Shouldha I actually go through it all？ Like， does anyone want me to actually go through it or shall I move on to the next part。

No， okay， yeah。 So it's just a process of like manually simulating what's happening。Okay。

 so the next part says that for the T cache。 And remember that the T is the two way associatedsoci of cache。

We observe the following five cash misses in order of generation， A， B， H， G， and E。

But unfortunately， our evaluation set up breaks before we can observe all the cache misses that occur。

 So using just the given information， which cash blocks are in the same set for this processor。

So now we have very little information to go off of， but we have to reconstruct what's in this cache。

So we， we actually have some information from the previous part as well， too。

 because so we know that these， we know these pairings already map to the same。

 to the same cache sets for。For the， for the direct map， for the direct map cache。 So A， B， H， D， G。

 C， and E， F。 And what this tells us is that since these are。

 since these eight are guaranteed to be contiguous in memory。

We know that for the two way associative the two way associative cache， if A and B conflict here。

 that means they have a spacing of four，4 addresses between them。

 And here they'll also conflict in the same set because by being four away。

 They're also they're also gonna be mapped to the same set in the two with two sets here。

 So A And B will belong to the same set。 H And D will be the same set G C and E F。

 So the same pattern is here。 So we can use that information in combination with these five cache misses that were' given to figure out which ones mapped to the same set。

 So I'm going draw an empty twoway set Associative cache here。

And we can go through and do the same process and figure out what's going on。So。Over here， let's see。

 Sha I write this down again。I don't know， is necessary。So we have our sequence， which is A， B， A， H。

 B， G。Okay， so， and and so forth， that maybe we'll need more later。 But so okay。

 so we observe these cache misses。 So we're basically going through this process of simulating this cache again。

And so we so A， so the first， the first program request is a。

 And so a is going to be brought into one of these sets。 And so we just assume the first one。 So。

 so A， A happens。 then B， and we ordinarily， we wouldn't really know which set B should go to。

 but because of the information from part A of this problem。

 we we know that B should go to the same set。 So B will be mapped in here。

 since we're two ways set associative。Then we have an access to a again， which is going to be a hit。

 Then we have H。 So we don't actually know what where H is going。 And so we。

 we have to look at the misses that we get。 So， so H is a miss because hasn't been seen before。

Then we have B。 And so B does not generate a miss。 And so that means B was not evicted。

 but B was also not the LRU here。 A was the LRU。No， no， no， Okay， sorry。 Yeah， B， B is the L R U。

 And so B， yeah， B would have been evicted by H if it mapped the same set。

 but it wasn't because B did not generate an additional miss there。

 That tells us that H maps over here。 And by default， we also get that D maps over here。So， okay。

 so that miss is H。 Then B is a hit because it's still in the cache。

 G comes in and G generates a miss。 So G， we we， we're not sure where it goes。

 H and H are still hits。 So that's fine。 So G could still be here。

 And it also could have evicted the LRU， which in this case， the LR U is B。

So then we have an access to A。 And so a does not generate a miss。

 which is fine because the LRU is B and A is still in the cache。Yeah， yeah。

 So then we bring an E and E generates a myth。 So E also gets mapped to one of these that we're not really sure which one。

 But we note that G and E come from different different pairings。Then， we have H。

Which H is already in the cache。🤧。This is。Yeah， I think I missed something here。So yeah B。

That means she wasn't on the first was second。That means G。Yet。

 G is required to be here because AIDs did not generate an additional miss。Before， before E， yes。

 So G is guaranteed to be here。And so that means C is also here。And H is paired with D。

 So D is D also maps to this set。 And then the only pairing left is E N F， which have to go here。

 So that， yeah， that basically gives us our， our different sets here。

 So we know the cache blocks that mapped to these sets are then A， E， B， F。And then， H D GC。Okay。

Yeah， so let's， let's go do this again。 This one's a little interesting。

 So I'm gonna do the same thing we did before。 I'm gonna write this down here and we're gonna trace the misses。

 So we have A， B， H， G， E， which are our sequence of misses。 Okay。

 so so we start off with an empty cache， so。😊，Oh we bring in A。 A is a miss。 We bring in B。

 B is a miss， and we know those go here。 Then A is a hit because it's here。 And A is now the LR U。

 right， So we've got to keep track of that。 Then H comes in and H generates a miss。

 So H gets brought in， but we're not exactly sure what H gets brought into。However。

 B is the L R U at this point。 And B， so the next access to B does not generate a miss。 right。

 That means B is still in the cache。 And B would have been evicted if H was mapped to this set。

 right， because B is the L R U。 So that guarantees that H has to be down here， right？

 And so we know that from from these these pairings up here。

 this gives us more information that we know D is in this one， too， right。So after that。

 B is a hit because B is still here。 And now A is the LRU， right。

 So I'm just going to write that down。 A is the LRU right now。And then we have G。

 G generates a myth where， we're not exactly sure where G comes in。 So G could be in either still。

 So G。Then we have an access to H， and H does not generate an additional miss， right。

 So H is still in the cache。 So H and H are hits。 So these two are hits。 Then we have a and。

A does not generate a miss， right， because the next miss is E。

 So we know that a is still in the cache， which means that anything new that had been brought in had been brought into the other set。

 So what we've seen now is that G。 So we know that G has to be here because otherwise it would have e a。

And then the next myth we see is E。 So this gives us A， B， H and G。

 which is basically enough information to put everything together at this point。 So A And B are here。

 H goes with D。 So H and D are here。 G goes with C。 So H， G， D C are all in the bottom one。

 And then the only ones left are E NF， which have to be up here because again。

 like these eight blocks are contiguous， right？ So， So that's how we get these results。 A E， B， F， H。

 D， G C。Yeah。 was was that clear to everybody， It's a little more confusing than the first part。

 So I takes more thought。对。Yeah。Y D belongs to H And G because so， okay So。

 so if we look at like what the addresses actually are， right， let's say that345。So。

 so we know that ABC D， F， G， Yeah， yeah， all those letters fit into this8 contiguous memory segments。

 right， So the eight contiguous memory locations。 So like we can just think about this being like I'll give an example。

 I guess。 So we could just think about。Sorry。Oh， yeah， yeah。 Okay， But but it's， it's all about like。

 you know， A And B would have to be off， off by four right。

 in order to map to the same set over here。Because you're using specific bits of the address， right。

 So it's like modular 4。 And here， this is modular 2， which anything that's modular 4。

 iss going to fit into here。 And they're gonna to map to the same set here as well。AndSo， yeah。

 it's pretty important that the eight are contiguous because if they weren't。

 then you have no way of really knowing anything。Okay。

 so the next part of this question asks you to write down the sequence of cash misses for the T processor in order of generation。

So we essentially follow the exact same prescription that we did here where we go ahead and simulate the cache。

 except this time we're simulating the T cache， Given that we know which one's mapped to which set。

So should I， should I do this or should I skip it， because it it's。

 it's literally the exact same thing。 You， you just。

 you just go one by one and track whether it's a hit or miss。

 And then you just seemingly get the stay of the cache。Yeah。Okay， so I I'm， I'm gonna skip that。

 so does anybody actually want me to go through it， Like， just raise your hand or something causeuse。

I， yeah， okay， okay， so I'll skip that one。 So then。The last part of this question asks you。

 what is the cache mis rate for each processor。 So they're asking us for D T and F。 And so we've。

 we've already done all this work， actually， So if。

 if we go ahead and look at this sequence right here。

 we know exactly how many hits and how many misses we get。

And they give it to us for the direct mapped cache。 So we don't have to do that。

We now know it for the fully associative cash， and we would have just done it for the two way cash。

 And so we have all that information。 So we literally just count up how many。

 how many misses we have divided by how many totally how many total program access there are。

 And it just gives you a number。 And so that would be the cash miss rate。Okay， yeah。

 so that's the end of this question。 then so。Yeah， do you guys have any questions or should I move on to the next one。

Sort of a story of the question。 but let me quickly summarize it for you。 So， so basically。

Here in the question， we have an architect who is trying to build a specific machine for high frequency stock trading。

 right and。Here are the two processor designs that this architect is considering using in in her system。

And here's some more information about like what is known for for these processors。

 but one thing that is unknown is the cache hierarchy or the memory subsystem。

 And this question is basically asking us to figure out what is the。

The cache hierarchy based on some experimental data。And so basically， this architect is running。

This application shown with this code over here to figure out those details of the micro architecture。

 So the program here is。Simple， it is basically doing random accesses over parts of the memory。

And there are two inputs to this program。 One of them is the stride。

 and one of them is the max address。 So when you look at the code， we see that。 So。

 So there is an sort of an infinite loop， like it loops for n times and。So first。The address， this。

 like variable is set to some random data and then multily it with the stride and。

Modulated by max address。 So what this means is if you， for example。

 have tried to set one and then max address set to 4。No matter what random data is generated here。

 the outcome will always be like accesses to address 0，1，2， and 3。 Okay， in any order。

 in random order。And then when the str is2， for example， and max address is still4。

 then the program will only randomly access0 and 2 right so you can like figure out what will happen when you change the stride and max address in different ways。

But at end， like what happens with this application is you just like randomly access specific addresses in the memory。

Okay， and yeah， as I said， the question is to figure out， like what is the， for example。

 the size of each level in the Kehe hierarchy， What is the access latency to it。

 detailstail like that。Okay， let me see if I missenting here。I don't think so is the question clear。

 And， and one one more thing that I have to， I I I I。

 I will emphasize is that this application runs for a very long time。

 So here assume n is something very big。So like the cache is warmed up。

 and what you observe in the data that I will show next is that state。

 like when the cache is warm warmed up completely。ok。And here， in this part。

We see some data obtained by running this application。For， for this processor over here。

And in the X axis， we see how the max address changes and different lines here show different strides。

 So strips 1，2，4， and 8 overlap here on the same curve。And then here we have Strtri 16 and Strtri 32。

 Okay， so it is like difficult to read this at first。 But if you like， go through it carefully。

 it's not difficult to understand。So here in this question。

 like one thing that you have to figure out to like quickly solve this question is like to you。

 you have to basically understand， right， So you have to understand how caching works， how like。

How access happens and how like data is brought from the main memory to different levels of the cache and how they interact with this subsystem right。

 So for example， when you have a cache head， you will have some like lower latency compared to a cache miss and this will change depending on how far in the hierarchy。

 you go through the misses， right， So let's say if you have three levels of cache。

 if you miss in all of them， you will have the largest latency when you go to the main memory。Okay。

 so。And here in the table are the parameters that we have to fill in。

 So there are some stuff that we cannot determine and some stuff that is not applicable。

 So you have to fill this table accordingly。 So if it's not applicable。

 you have to write down that if it's like not。If it's not possible to determine based on this data。

 you can just put X or like indicate that。Okay， so let's start with reading this this plot a little bit more。

 So here we see like some interesting points， right， So until this point over here。

 the latency is constant。 It is 20 nanoseconds， right after this point， it starts increasing。

For strides of 1，2，4， and 8。So this is actually showing us。The size of the。First level of cache。

 right， for for， for， of the L1 cache。 So when the stride is one， you。

 you basically can access every。Cash block in， in the max address region。Right。

 so you have that ability to touch every single cacheline because you are just randomly selecting the address。

So this str one is interesting to look at here， basically until we reach this point。嗯。

After running the program long enough， we cache all the data， successful and only access L1 cash。

 we always have a hit， right。 But once we。Get to 32 B。We start seeing cache misses。

 So the latency increases here when the strike is one。

 So this means that we are touching two times more cache lines than can fit。In the L1 cache。

Is this clear。Okay， so this， this question， in my opinion， is the easiest to solve。

 but requires a lot of thinking。 So once you like， understand that it's， it's very easy to like。

 make those observations and determine like， what is the one size， what's its latency。

But I hope at least the latency is very easy to find trial。

 So L1 latency is this basically the point where you。

 you' like region you are accessing is well very small。 So it all fits in L1 cache。

 This is your L1 latency。Is there a question？Okay， yeah， so basically， let's， let's put that in。

 So the latency is 20。 And here access latency from is defined as。 so it's basically。

Latency that excludes other levels。 right， So if， for example， you are filling in L 2 access latency。

 you have to subtract L 1 access latency from it。 Okay， so this is like just that level。

 but not true the hierarchy。But for L1， it doesn't matter， it's just 20。And then total cache size。

 So as I said， you can determine it based on those two points， right， So it has to be 16 B。Right。

 if it's small than 16 B， then the curve would have looked something like this。

 So you will have some change in here。Or if it was larger， you can fit more data。Okay。

And then Ke associivity。 So this is a bit more difficult。嗯。So how， how。

 how you can tell this is by looking at the other strides。

 So one thing we see here is that when we increase。嗯。Stripe to 16 and the max address to。

2 to the fifth， which is like 32 B， right， So we have 16 B of stride。

 and we are accessing total of 32 B of a region。 So basically。

 we are accessing only two addresses in this case， right。

 because we are accessing at 16 B granularity。 So in this case， what we see here is that。For 16。

 we can have。Like both of those two cache lines in the cache， you can fit to both of them， right。

Because the latency is just their long latency here，20。

This basically means we have to have two ways in that cache in order to fit those two cache blocks。

 right， otherwise， otherwise。Since those two addresses。

 we will map to the same set because the size of the cache is 16 by。 right。

 They will discard discard each other when you access them。 But that's not happening。

 So then the cache is looking something like this。You have two sets， and we don't know how many。

Sorry， we have two ways and we don't know how many sets we have。So the cash association， too。

And for the cacheline size， so this is a bit more difficult。

 but it's not possible to determine based on this information because like if you test it you will find that even if you make those like two bytes each and then you have four sets in total。

 it will work， it will generate exactly the same latencies。

 if you simulate like with different strips and different max addresses here。Okay， so basically。

 this is not possible to determine given this information。So， another thing to。

Obsserverve from this plot is that there is no。Similar peaks here， like going up in this plot。 right。

 So if it was like， if there was another level of cash。We would have had a another。

Like straight line over here until some point where we saturate this next level of cash。

 And then it will again， continue rising after filling up that cash， right， So basically。

 seems like it just directly goes to。嗯。Like this lant over here， without any。嗯。Such。诶嗯。Such behavior。

 like in here， we can tell that there is no another level of cash。

 but we directly access the main memory after， after we we missing L1 cache。 Okay。

 so all those parts are not applicable， basically。 and the du latency is。Hundred， nanoiseseconds。

 right， Because the max point we get is this。So it's like 1，20-20。 And total size。 we don't know。

 What's the total size of D M。So this is not applicable for year， right。

 There is no like something like cash asivity and same for the cacheline size。 We don't know that。

Okay。So like those four things are the only stuff that we can say based on this plot。Yeah。

 so why don't we know。So why do we know that there's no adult cash but I can't be like a really big。

嗯。Sure。It could be a very big cash， yeah。ok。と第は。Yes， yes。But。Yeah， maybe。

 maybe you'll be confused in the beginning by that。 And， but after seeing the second part。

 I think it makes it clear because in the second part we have。 But there again。

 you can claim that you have another level of， okay， yeah， I， I think you're right。 Yeah， so you。

 you can say that。 Maybe it's a very large cache。

![](img/4aaa0601442398c4153434b16b486e27_13.png)

Okay， and then this is the second part。 So this is the other processor。

 And you see that here we have more variation in this course。

 So we we have that like sta like behavior here， right， So we come to this point。

 the latencies start increasing。I think this thing is shutting down。 I over time。

 I'll just cancel it。Okay。嗯。Okay， so we have two of those like peaks over here， right。

And this basically， like from what we learned from the previous part。

 we can now tell that or this processor must have two levels of cash， right？ And then basically。

 in the same way， we found the size of the first level of cash。 you just look at this point。

 like the point where the latency for straight 1 starts increasing。

 right So that is basically the cache size。 It's 32 B。And the lat is 10， in this case。

For associivity， we do the same， right。 So what we did last time was looking at the max address。For。

 for a stride that can still fit all of its data in the cache。 So it is 2 to the 6， which is 64 B。

Right， with 64。嗯。Side。And we see that。It can still fit the cache line when it's accessing only one cache line。

 But once it access starts accessing two cache line over here at this point， the latency increases。

So basically， you don't have any room for。So we don't have any sensitivityivity here because two catch lines cannot map to the same set。

So this is how we tell that we have cash as of one。And the cache line size is， again。

 not possible to determine from here because of the same reasons。 And for L 2。

 it's basically the same that we do。 But instead of looking at this part。

 we are looking at this part now。 So straight straight 1 starts increasing at this point。

 max of 2 to the。9th， which is 110， sorry，512。byte。

 so this is the size of the next level of cash and the latencies。 So the total latency here is 50。

 including the L1 cache。 But it is asking us only the latency from the previous level。

 So this is 40 nanoiseseconds。 Okay， and then we don't have anything else here。 It is the Dm。

 So we know that it is1 hundred nanoiseseconds。And。Yeah， we don't know its size。

 We don't know anything else here for the assistivity of the。Second level of cash。

 We can again do the same。 We can look at this point over here， where the first strike 2，56。

And the area。Sorry， the max address of。1，1024。The latency is preserved， right。

 So this is the L2 latency in this case。 So with this stride and this max range。

 we can fit four cache lines， meaning four of those cache lines。Can map to the same set。 So for to。

 to be able to do that， we have to， this cache has to。Have for。ways。Okay。

So the same thing I did here。 And again， we don't know the cacheline size of the system。So basically。

 this was the second and last part。Any questions about this。

 So I think this is a bit difficult to understand。 I will suggest you to like。

 try to do it yourself again from scratch。 although you see the solution now。

 I think that will help you like reason a bit because like reading this graph is not trivial。

An architect is designing a preagege engine for his machine。

 he first runs to applications A and B on the machine with a straight pre application A and B both are accessing an array A of housing U A element。

 the only difference between application A and B is while the array indice of application A is implemented by4。

 the array indiceice of application B is multiplied by4。

We know that I and some are in registers while the RAA is in memory。

We also know that a cash block is of for byte in size。The first question is。

 what is the pre accuracy and coverage for application A and B respectively using a slide？😊。

Now to understand the coverage accuracy of a stripe pre in application A and B。

 let's first try to understand how many memory accessors application a would generate application A would access elements is zero。

业父。E8。A 12。And so on。So this means。In total， application A would create。Housing divided by4。

 that's 250 memory requests。Out of these 250 memory accesses， the first two axis。

 which is going to a0 and a4 won't be predicted by the prefecature because the prefecer won't understand this is the first stride off for cacheline。

Then once it loads the strike， it can pre fetch cash line a882 will and so on。 In fact。

 the prefeer would preface the cash line a housing and also， which would be required by the。肉。

So in total， the prefeure would generate。读。🎼我见你。Prefes as for the formula wheel。

 we know the accuracy of a preship is number of。Reit。Which is used by the program。

Vided by the total number of pre。As per this rule， the accuracy of prefecual a。

The accuracy of strike prevention。In this program， a would be240。

Eight out of2 49 because the last pre， which is going to add in element 8000 won't be used at all。

Similarly， the coverage of the program， the coverage of the precture is defined as the total number of memory accesses。

Which is predicted by the profession。Divided by the total number of。Memory accesses。

As for this definition。The total number of memory accesses would be 250。

Out of which 248 would be successfully predicted by the prefe hence the coverage of strike prefecture in application a would be 248 25 now let's see what would be the strike prefes accuracy accuracy in coverage would be when application B。

As we can see， application B will access the RA element a1。If full。Is 16？A 64。And a2 56 only。

So that means in total。The program would make only five memory accesses。But in this case。

 there won't be a constant slide between these accesses and as a result。

 the slide prefecure cannot prefedge any of the cache line and the prefetage accuracy。

As well as coverage。Both will be zero for application B Now let's go to the next question suggest a prefeure that would provide better accuracy and coverage for application a Now recall that for application a the stride prefeure fails to prefe memory accesses which is going to element a0 and a foot because these are the first two accesses which is giving us the stride learning but the next block prefeger would always preface the next cache block without even looking for a constant stride hence in this application a a next block prefe would actually successfully prefge to 49 out of two。

50 memory accesses， whereas249 out of 250 prees would be correct So in this case the prefe' accuracy would be 249 upon 250 and prefes coverage would be。

2 49 by2 50 again so a next line prefeure would work better than strip prefecure for application Now let's suggest a prefeure that would provide better accuracy and coverage for application B most common prefe such as stride stream next block prefeure would not improve prefeure accuracy for application B as application B does not have an access pattern for which prefecs are commonly designed So in this case some form preexution waste prefeure like run ahead execution。

Could help improving prefiage accuracy Now let's go to the next question Would you suggest using run ahead execution for application A if yes then why。

 if no then why not， as we know， run ahead execution could still provide good prefiage accuracy even for application A which has regular access pattern but in run ahead execution it might not be possible to prefidge all cash blocks before they are accessed as run ahead execution happens only when the application is stall on a cache miss So in this case for application A a strip prefeture or an H block prefection could possibly prefedge all cash flow before they are accessed as prefiting happen in parallel the application execution so for application A run ahead execution will not be suitable but in the case of application B whose access pattern does not have a regular strip commonly used prefes are not designed to prefe and access pattern like this So in this case run ahead execution can potentially。

Pfi some of the cash block and this is all especially true as the address of the cash block in application B does not depend on the data from a pending cash base so for application B。

 we would still suggest going for run ahead。

![](img/4aaa0601442398c4153434b16b486e27_15.png)

2 is cash performance analysis。 And this question， would we。Do is。Do some some microbeching。

 This means we are going to execute a specific program。

 short program that is going to exercise some particular features of the of the cash hierarchy。

 It's very interesting this kind of microbech is very useful because it usually allows us to do some reverse engineering in systems that we don't know how exactly they are built and。

After getting this knowledge， we might be able to optimize our code， for example， better。So。

As you can see for this micro range marking， we are given two codes。Cold 1 and code 2。

And we are going to accessing these codes to one array data that contains 4 byte elements。

 So this is 32 bit and sine integralgers。Just there is an note here that says in order for you to know。

 don't care about that， that this latency array， the accesses to this latency array where we are going to store the latency of each memory access is is not cache so its accesses bypass all the caches。

And timer， as the question says， it's going to return a timet。 So if we go through code A， we。

 we will see that we go through the。Aray data with a certain stride。And。

We record the timestamp in the right before the memory axis and right after the memory axis and then this way we calculate the latency in the code number two。

 we have two loops。 the first loop is similar to the to the to code one。Actually。

 both loopbes are the same The only thing that changes is the size that we are accessing here is size one and here is size2 with the stride one or with the stride2 as you can see is in this loop2 where we are going to measure the number of cycles that we need。

As the question says， the cash hierarchy has two levels。 so we will have our CPU。L1ang。L 2。

And main memory。And we also know that the size of this L1 is。4 k。Part A。

Says that we run code 1 and we obtain this chart that you can see。You can see in the screen。

So in this chart， what we can read is the latency。Of every memory axis for 64 memory axises。

 Keep in mind that these memory axises straight and these memory axises is one。

 So straight is equal to one。What what happens here this part of the question ask about the cash block sizes in L 1 and L 2。

 So what happens here。We should infer whats what happens from the latency values that we see in the chart。

 As you can see in the chart， there are three different latency values。700。300 and100 cycles。

So this give us an idea of which。Part of the memory hierarchy is being accessed。 Obviously。

 L1 is closer to the CPU than L2 and L2 is closer than than the main memory。

 So it is suspected that these lower latency 100 latency 100 cycles correspond to L1。

 the 300 cycles correspond to L2 and the 700 cycles correspond to the main memory。And actually。

 exactly what we， what happens here in the first， the the very first。Access。EWhen I is equals 0。

EWe will have an L 2 cache mes。 For example， this cache blogging in memory。

Will be brought to L2 and also to L1。EAnd because we have Al to Kashmis。

 that's why we see this e latency of 700 cycles。Keep in mind that the next axis is with a stride equal to one。

 So it's exactly， so it， it's exactly the next four binds。

 The next four bys that are also in the same cash block。

 So that's why we see this shorter latency of 100。 And we。See the same latency for the。Next7 aes。

And right after death。300， the latency is 300。 So this give us。诶。This give us the answer。

 actually for at least for the cash block size in L 2， which is。For8 memory axises is。32 B。

So in耀guang。We are using blocks of 32 B。What happened what happens in L 2 observe that。Access。

 memory access with I equal 8。Has a latency of 300。 So it's hitting L 2。

And then we again have 7 accesses to L 1 because the latency is 100。 So this means that。Another。L1。

 cash block。Is being fetch from L 2 to L 1。With。This memory access， memory access number 8。

 That's why we have then。Saving heats and。Then we have again， a yellow one M an L2 heat。

We are all another L2 hit here， and here。Again， we have a means in access number 32， which is。128 B。

 And that's why we can infer that the L 2 cache size is 128 B。Is it clear。O。

So then let's move to part B。In part B。The question is。

 we are using code 2 with a Str 1 equal to Str 2 equal to 32。ESize 1 is 10，56。 you have one question。

Part A。呃，以服呃。So actually， we， we yeah， we expect from you that you answer。 I mean。

 you explain briefly what this is about， you know， it's not just saying 32128。Yeah。Okay。Yeah。

 and as I was saying， in part B， size 1 is 1056。 size 2 is 1024。And in this case。

 we observe that latency0 is equal to 300 cycles。 Keep in mind that latency 0 is the value that we obtain in this array latency for the very first axis in this second loop。

So latency 0 corresponds to I equals 0。嗯。The so the question the question continues says， however。

 if size is equal 1024， latency 0 is 100 cycles。 And the question is。

 what is the maximum number of ways in L1。Okay， we can assume that the replacement policy is 54 or LRU for now。

 so we know that because we know the size of the cache。

 we know that there are 128 blocks in the cache。And we also know how we are accessing this array data。

 right？let's say that these are。This is our array。And with a stride and。

 and each of these rectangles represents one block， one cache block in the first path。

 in the first loop of code 2， we are accessing with astr 32。 So this means that we read this element。

 this element， this element， and so on。And。The question is。If the size of the array is。10，56。

If we are accessing up to 1056 element or size 2， sorry， size 1 is equal a equal1056。

 we are going to obtain latency equal 300 cycles。 observeerve that here。This is 1024。

O serve that here。We have 32 cash blocks。So the reason why。We measure latency 0 equal。

300 cycles when size 1 is equal，1056 is because this last cash block。Is replacing。Cash block 0。Okay。

So， that's why。EWe miss in L 1， but we hit in L2 in case only。This part of the question。

 in case only。32 Caues are accessed， because size 1 is。10，24。This cache block is not being accessed。

 so it is not replacing cash block 0。 So that's why we hit when we access element 0 for the second time。

So from this， we infer that。The maximum number of ways。Is 32。O。翻译。You don't have any questions。

 Let's discuss。part C。So in part C， we again use code2。

 and we are also going to use code one after that。And with， what we want to figure out is。

 what is the replacement policy， We already know that the replacement policy is going to be 50 or L U。

 because that's what the。What the part B told us。But we don't know exactly yet。 So that's why we do。

 we run this different experiment where we first rank code2 with。

A strideide 1 equal 32 size 1 equal 1024， straight 2 equals 64 and size to equal 1056。

 So now you array data。哦。like this， again。1 56。1024。This is zero。So in the first pass。

 in the first loop of code 2。We are。Accessing this element。Les。任秋龙。Re callll that。

 we know they actually the。Yeah， the question tells us that the associivity is the maximum obtained in the previous part in part B。

 So we know that the associivity is 32， right。So as I， as I was saying in the first loop of code 2。

 we are accessing these elements。In the second。Loop of code 2。 Now， the strike is 64。

 So this means that。We read here。And here。Here。And so on。So。Observe that。After running code 2。

 we run code 1 again with a strike 32 and again with size 1024。

 And we observe that latency 1 is 100 cycles。 Latency 1 is the latency。Of this。Memory access。

In cold one。So if， if it's 100 cycles， this means that。Wei。Find this cash block in your 1。

So even though this cash block。Was not accessed in the second loop of Co2。

I this is still in the cash。So， it has not been replaced。

So that's why we know that this cannot be L R U， because if it were L U。

 it could have been replaced and。Their replacement policy is fiveful。That如给。O。So if A。

 B and C was clear， if you understood L， B and C， then part D must be easy for you。

EIt says now we carry out two consecutive runss of code1 for different values of size。

2 consecutive runss。In the first run， a stride is equal to one。In the second run。

 stride is equal to 16。 We ignore the latency results for the first run and average the latency results of the second run。

We obtain the following graph。EWhat do the four parts shown with the arrows represent。

So keep in mind that in the first part， in the first rung of the code， caches are called。

 and we are going to warn them that right。 we， we are going to load。Cash blocks in， in the。

In the caches。 And after that， we run the same code for the second time。

 So we are going to find some heats and misses， right。

 So some of the cache blockss will be in the in L1 or will be in L 2。 we might find them or not。

 So we will see observe also that the interesting part here is that we don't know exactly what's the size of the caches。

 Well， we know that L1 is 4 kB because that the question is giving us this information。

 but we don't know what's the size of the cache And you obviously don't have it here in the H level。

So， but it， it's something it's clear。Here， latency in this part， first part before R01。

 the latency is 100。Betweenarrow。2 and arrow 3， the latencies300。 and afterarrow 4。

 the latency is 700。 So it is clear。 and also keep in mind that in this plot， in this graph。

 we are averaging the latency results of all the memory axises。

 This means that all memory accesses here hitting L1。Here we find heat S2， and here misses single2。

 and we should access main memory for all the memory accesses。So what happens in this part。

 even though in all these experiments。In all this flat part of the curvep， In all these experiments。

 we have latency equal100。 What happens is that the size of the array。

 whether we are accessing is smaller or equal than the cache size， right than L 1。

 So you can be sure that。This point here。That R 1 indicates is 4 kB。

 So this would be a good way to know what's the size of， of L 1。That's exactly the same for。R 03。

This is the size of L 2。So this experiment is good to know what's the size of L 2， right。

 or to confirm what's the size of L 2 if we really knew that。And in these parts， between。

R 1 andarrow 2 and between R3 and R 4。 What happens is that some cash blocks hit。

 So we have hits for some cash blocks we have misses for other cash blocks that is also related to the replacement policy that we are using and the larger。

The larger they array。The more cash misses that we have in L 1 or in L2。Okay。



![](img/4aaa0601442398c4153434b16b486e27_17.png)

question we were given basically access pattern， the addresses。 So which are basically in B fashion。

 So， and the question asks for us， like， we need to come up with the cache design。

 given given those access patterns。 So in the。So here， actually， let me explain it first。

 So basically， these are the excesses。So these are the addresses accessed from all those two young。

 And then we， we are given with the heat rates as well。 And also。

 these are the sequences of these excesses。 But the important thing is that there are no other address excesses between each sequence。

 Basically， these are back to back。 So these， these are the things that we need to know。 And for。

 for the first question， basically we need to figure out for the， for the cache block size。

 So for this one， actually， we can。Try to do brute first。

 And then we can try each of the options here。 So is。

 so let's first assume that we have block size of 1，2 and8。So if that was the case。

 then for the first sequence， for0 will be always a mis， right。 So this is always a miss。

 So this is our first miss But if， if it is 1，2 and 8， the 4，8，16 and。64 will be a hit because this。

 this will be located in the same block as in 0。 So we have basically here4 hits。

 But whereas in the first sequence， the question says we have3 hits because we have 6 x design。

 The hit rate is one divided by 2。 So this won't work。 So let's try 64 for this one again，0 is a ma。

And again，4，8，16 and will be a hit 64 and 1，28 will be misses。 So this kind of works Okay。

 so let's try32 again。 So 0 again， miss。 So 4，8，16 again， hit hit and the rest again， are misses。So。

 so this also works kind of for now。 And for the， for the last option， we have 8 and 16。

 But for these， see that okay， will0 will be a again miss for both of these。 and but for。

For both of these， actually， we won't be able to include。16， so basically。

 we will end up with the atmost two hits。And this is not gonna work as well， at most two hits。So。

 okay， so we are in between 32 and 64。 we need to look at for the second sequence in order to say that。

 okay， it this is the， this is the case size。 So for this one， basically。

 the hit rate is 5 divided by 8。And so we need to first look at。The those addresses。

 because we basically are sure that those won't be in the same block when they are first accessed。

ESo for the 8 K， this will be a miss。S consequence。For the first 8 K， this is M。For the first 16 K。

 this is also miss。And for this one。For this one as well， this is also miss。For sure。

 So these are all misses， so， but。Again， then the rest of these need to be a hit for us。 Okay。

 so in order this to be happen to happen。 Basically， our case size need to be 64。 Why if this was32。

 then basically 63 would be miss。Because we don't basically access any address between 32 to 64。

So in order this to happen basically， our case size need need to be 64 so that we will also have this 6 to3 as a hit。

 Alright， So， okay， then 31 and 63 will be hit for us。But here also，64 need to be a hit。

But our case size is 64。But the thing is that so you need to get this。 Basically。

 we previously the excess 64。 So this is already in the cache。 So this is also a hit as well， okay。

So our case size is basically then。64 B。All right。So the second part of the question。

 So this is basically， we are asked to find out the case associivity。 So we're gonna do the same。

 Basically， we're gonna try all of these like one associ to associative。 So for this one， actually。

 we need to consider the the the total case size。 Okay， it's either。It's either for。

Is either 4 k pairs or 8， right。So for this one， if this is one associated with a cache， then。The。

 the for the 4 kB case， all the multiples of 4K address excesses will be will will basically try to access to the index of 0。

 right。And for the 8 K， again， it will try to access to the index of 0。If， if the case size is 8 kb。

 So we need to keep this in mind first。 And then let's assume that this is one way associated。

And basically， write down all the excesses。Here。Let's write down all the excesses that are multiples of 4K。

ok。So， these are basically。For for。0， I'm sorry，8 k。sixteen k。4K。8 k。And 16 K， right。

So if this was one associative。 So for each excesses， we would be replacing the index。

 basically index block， right， so， but。But。But remember that。I'm gonna show it here。 So those things。

 these excesses need to be a hit in order to have 5 fit， basically， right， So it cannot be one way。

 So because those will be removed if it is one way。Right。So， basically。And。When I access 8 k。

 it will be replaced with this one and 60 k replaced with this  one，4K。 And again。

 when I access the 8 k， I will basically， it， I will be， this will be basically a miss。

 and then I will basically replace 4K and then put to 8 k。 So let's imagine4 two way。

And the ways are either。The ways are either 2 kB or 4 kB， right？ So basically。

 I'm gonna consider all the excesses of all the multiples of2 kiloB here。 Again。

 I'm gonna do the same thing that I did here。 So the multiples are basically the same0。8 k。6 k。嗯。4K。

H k。16， I think I need to write more。佢 the two k。And8 K， I guess。right。哦。O。Yeah， this was， yeah。

 this was one。 So this is actually， the explanation is kind of similar to the one that I did here。

 So for the actual， for the four way， actually， you can also consider。63 here。

63 will be a miss as well， because I'm gonna replace 0 with 8 k。 and then 63 will be a miss。

 And then this will again reduce the number of its here。 So for the four way， two way。

 it's kind of similar。 again， these are the excesss。 And for two way， actually， I will have this one。

And this one for the first two access。 And then I'm gonna replace 16 for either of these。

 And then again， replace 4K for either of these。 So this will make us like。For sure。

8 or 0 will be gone， basically。Actually， both of them， right， so。ESo when I try to access a here。

 So this won't be in the cache。 So this will be a miss again again。Alright。

So two way doesn't work as well。And， one way also doesn't work。So， let's look at8 way。

So I'm gonna write all the。 So for8 way， then the the size of each way is basically either。

512 or 1 k。Depending on the case size。 But basically， we don't know it yet。

 So each way is of 512 or one k。 then given this， I'm gonna basically write again。

 all the estases that are in multiples of 512。 So these are。Again。16 K，4K，8 k。16 k。呃。哦。有 the two k。呃。

one k。8 k。So， basically。What I did was， so I picked all the excesses in order in order 0，8 k，16 k。

4 k，8 k， again，1632，1 k。 And this is also a multiple of1 1024 and also 8 k。

 So these are the excesses that will map to the same index in this order。 So if this was a8 way。

 then this would be in cash。 Again， this would be。So。This is， again， in cache。

 So this is already in cache。 This is already in cache。 So this will be， again。

 that there is a space to put it in the cache as well。

So there is also still a space to put this 1 K address access into a。And， and also。

 there's a space to put 3 K into the cache again， because this is a8 way associated cache。

 And all of these actually have the same index， basically。 So what does it mean。It means that。

So if you consider the sequence 3。So the our hit rate is one divided by3。

So then this means that I only have two hits。So let's first find out the first it that is for sure will be a hit。

 which is 129。 Why basically the， the reason is I already access 128 here， right。

So when I try to access 1 to 29 here。 So this will be for sure I hit， okay。So。Then。We， we don't。 We。

 we shouldn't。So the， the options are basically。Either of these， just one of these should be ahead。

 not， not multiple of these， al right。But。See if this is8way Asciative case， cash。 Basically。

 I will end up with。Having 8 K as a hit， because this is already in the cache previously。 Alright。

 So again，8 way won't work for us。So。但。4 wei。Is our own option left for this one。So the case size。嗯嗯。

So we know that this is a four way。And b is 64 by。And we are asking if the case case size is either 4 or 8 kbys。

 so。So here， then， the ways are either。1 k。Or。The， the 2 k of size， right。

 The size of the ways are either 1 k or 2 k， Given that case is either the case size is。

 is either 8 k or 4 k again。So then what we need to do is basically， we need to consider。对对。Actually。

 all of the sequences。 But we're gonna focus on the third sequence。So， let's。Yeah， let's。Again。

Write down all the。Sequences， the the the addresses that will map to the index 0。

Which are basically the multiples of either 1 k or 2 k。So those are will be again。

 So we are doing kind of the same thing again and again。this is 0。And this is 8 k。s k。嗯。4K。e k。16。

22 k。So here comes the trick， basically， So 1 k and 3 k。Our will map to the same index。If the way。

 the size of the way is 1 K， basically， if the case size is 4 kB。 So this is only possible if。

If the case size is 4 kB。 Okay， so this won't be possible if case size is 8 kb。

 So because it won't matter to the index 0。And for， for 8 k， again， it will map to the index0。 So。

 okay， we know that this is4 way。 Then this will be in cash。 This will be put in cash。

 And then this one， this one。And this one， right。So。Yeah， the， the。

 the the all the ways for the index 0 are full in the cache。So 8 k， again， it's in the cache。

16 k iss in the cache。 So 32 k。 So for the 3 K 2 k actually， we're gonna。

 I forgot to write down 0 here。 There's also 0 there after。After 32 k， there's a0。

So even if the K the， the replacement policy is 50 or L U in， in either of the case。

 we're gonna reply， replace 0 for this one， right？ So  for the32 k is not in cash。

And then those are in cash。 And then I accessed 8，16 recently。 and also 4 k recently。 So basically。

 this is the least recently use。 And also， this is the also first one that put in the cash put the cache。

 Basically， I'm gonna replace this。 So this one be in the cache。

 and total to total to will be in the cache。 So for0 again， this is not in the cache。Basically， so。

So what we know is that0 is for sure M， okay。Cause remember。

 we were saying that the number of hits are 2 and 1，229 is a hit。

 And then is either 0 or 8 K will be a hit for us。 And then we now figured out that 0 is awesome。

 And then。8 K。 does this one have to be basically a hit。

So this will be crucial for us in this question。 So why is the case。Because。If the case size is 4 kB。

 basically， this is not indication。 And this also maps to the index of 0。 So basically， I'm gonna。

I'm gonna， basically。Remove this one。Or， or this one。So either of these， if this is54 or L R U。

 the the the either of one will be remote。 So 1 K will be put。 And for the 3 K again。I'm。

 I'm going to， I'm going to replace。Eith4K。Again， because this will be the least system to used。

If it is not 16， let me see。 we access 8 k，16 k，32， and this one。 Yes， so 4K。

 either 4K will be removed。Or， or 16 k will be remote。 So basically。

 what this says is that the cache polish replacement positive is 5，4 or L R U， basically。8ight。

This8 address of8 will be removed along the way。 Okay， this won't be in the cache。

So why this is important。 So if the case size is 44 kB， and this means that we will。

 we will have to replace the address of 8，8 k。 And then this will mean that the 8 k here will be a miss。

 So this shouldn't be a miss。Why we are already given with the heat rate。

 And our only option is a 8 K should be a hit。 And then this means that。Case size should be 8 kB。

 so that。Those one won't map to the index of 0。Indi caches， okay。

 not index of 0 so that I will be able to access 8，8 k。So， this is。This looks a bit tricky to me。

 at least。呃。So， the last question。

![](img/4aaa0601442398c4153434b16b486e27_19.png)

So we know that the case size and the case sizes。8b。 So we know that the case size is 8，8 ks。

4way asciative。And the block size is 64 B。Rightright， I yeah， I got， I got through。 I guess yeah。呃。

Yeah， let's do the same for the one last time。So I'm again writing all the address exercisees that will map to the index of 0。

In a sequence。8 k，16 k。22 k。0 N N H K。 And this is4 way， right， So those are all。In the cash。And。

 and if it is， yeah， this is 8 K， this is in the cache。 But if it is L R U， then this is the。

 this is the one that is recently used。 So 8 k in the cache，16 k in the cache。32 is not in the cache。

 So basically， I'm gonna replace 0 for the reason that I just discussed in the previous question。

 So 0 will be replaced 32 in the cache。 So for the 0。 So if it is 54。Then we will have to remove 8。

Again， but for the same reason that I described here， it should be a hit。

 Then this shouldn't be a 54。 This should be the replacement policy。

 should be least recent to use so that I wont remove 8 K instead。呃。Instead。

 I will remove 4K because this is the least reason to use， okay。And then， and then this will be hit。

Alright， then the， and the policy is。Aller you。Right， this was mostly。Oral explanation。

 rather than writing all everything here。Mathematicically， what I hope。



![](img/4aaa0601442398c4153434b16b486e27_21.png)