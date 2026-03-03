# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P33：Chapter 3 6.Flip-Flop Variations.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/b75e559fcc458b3099d0d34663bb31c5_0.png)

Let's talk about a few variations on flip flops， so remember that flip flops are the state element that we're going to be using in this course。

😊，And it's important to understand the other state elements。

 because the flip flop is basically built from those other state elements。So here is a register。

 And in this case， it's a4 bit register。 So a register is just a group of flip flops。

 or it actually could just be a one bit register， too， which is a single flip flop。

 So here is a4 bit register。 And means see， it just has four。Flip flos。De foot bos。

And when we say flip flop， it also just means D flip flop。

 So we refer to it just simply as flip flop or flop even。And these all share the same clock。

 So the clock comes in to the input of all of those clock inputs。 And we can equivalently。

 So these are equivalent circuits， Draw the four bit register like this， where we show a bus。

This is a four bit bus。 In other words， this is equivalent to you four wires。

And so we put as a kind of。A line here with a slash through it。 And the number 4 indicates。

The equivalent of four wires， because it's more concise and easier for us to draw， right。

 with for a4 bit register， not a big deal。 But what if I'm now changing it to a 32 bit register。

 This is easy here。 Oh， actually 1 to 32 B register。 Iright， it's 31 to 0。 It's 31 to 0。

And I change this into a 302 way register。If I want to change this， this picture。

 now I have to draw that 28 more times。 So equivalent， right， These are both four bit registers。

 but will most often use this symbol because of。Because it's just easier to draw。

 especially when there are a lot of bits。We can also build variations of flip flops。

 So here is an enabled flipflop that has。😊，The regular clock and D inputs。

 but now we have this additional input， the enable input。E， N， or sometimes just labeled E。

So here's our symbol down here。 we have our usual inputs and output Q。So D clock， D and our output Q。

But now we have this extra input， this enable input。

And so enable controls when new data is stored or held in the state element in this full thought。😊。

So when enable is one。The flip flop acts like just a regular D flip flop。

Q gets the value of D at the clock edge。But when enable is0。The flipflop retains its state。

 So Q gets Q previous。 even if there's a clock edge， it ignores what。

 what value D has and is not enabled。 So an enable is 0。 the flip flop retains its state。

That's previous state。And so。诶。Well， how do we build this？Well。

 we could start with a regular D flip flop。Here we have our regular D flip off with D input and Q output。

And we， well。We want to feed something into D N to have it make it do。You know。

 what we just described up here。And so we could draw a truth table。

So this is this DN is what we're feeding into the D input of that flip flop。

And this D N is gonna be the output of our tree table because we're trying to control that。

 And we could say what is the enable input。 So when enable is 0， what do we want to feed to D N。

 Well， we want to retain its previous state。 So we want to feed Q previous。

Into that D in input so that the next clock edge， it will just retain whatever it had before。

And when it enables one， what do we want to feed in there， just D。

 right we want to sample D at the clock edge。And so now we can write an equation for this。😊，And say。

 okay， well。Let's putut this in a different color here。诶。D in。Is equal to。Well， enable bar。

We're doing this， this row here。 En bar。 So enabled 0 and。He previous。Or。Next， row。Enable。

 enables one。Here。And the。And so， we can。Put our an gates here。And we have enable coming in。

It's our new input。And we have D， our usual D input or data input up here。And when enable is one。

 enable and D， there's that top。And put， and we might want to put a little origgate here。

Orre these together， or enable bar and。He previous。And so now we can kind of abstract this all away。

And now， we just have our。Usual inputs here。 Let's connect that orgate。Clock。D。

And now we have this extra input enable and our output Q。

And we could have done this in a different way， right， So we could have drawn a truth table。

 Let's draw different truth table to show all of these。 So enable。And Q， for example， or Q previous。

Right， on dependent on the clock on the clock edge， right， when next clockage。

 we get this Q is the previous value of Q。 So that's why we call that Q Q previous because when we get this。

 the next clock edge。That Q that we're using was the previous value。Okay。

 so let let's do this more complex truth table here。 We're going to end up with the same thing。

 but when enable is0。Doesn't matter what D is。If Q previous is 0， DN should be 0。 enable is0。

 don't care。 Q previous is1。 DN should be one。So should follow whatever Q previous is。

What enable is one。And D is 0。 We don't care what Q previous is。TheN should be 0。What enable is one。

And D is one。Doesn't matter what Q previous D in， what we feed to which should be one。

And so now we can do the same thing that we did before with this kind of condensed truth table。

 variable enter truth table。We're going to do summer products form and grabs our ones now。

 So that one is， I'll draw it up here。D N equals well， enable bar。And。Q previous。Or。

Let's grab that bottom one here。Enable。And D。And so we end up with this exact same equation that we got with the condensed truth cable。

 So whichever one， you know， you feel more comfortable with， feel free to use。😊。

This one is a little easier to draw this more condensed one and easier to get the equation。

Not much easier， so so it's really your call。Okay， let's show yet another another way of finding what this。

How to build this circuit。 So we'll again， start with our。Multulipex are here。I mean。

 I already just gave it away， but our def flip flop。Our regular default flop。

 And now we can actually put a multiplexer here。 and the enable signal is choosing what we're going to feed。

😊，To our flip flop。 So this is still our D， N。And what we're going choose。 Well， if it's。

 if it's one， we want to feed D into D N， right， just acts like a regular full flop。

 So D should go pass through。To D， N。But if。Enable is0。 You want to pass in。H previous。

And so in terms of， well， ease of understanding， this is probably easier to see exactly what this enabled flop is doing。

But it's going to use， you know， or could potentially use more gates in the multipleer， depending on。

 yeah and how that multipleer is built。So here's that implementation drawn out there。

Another flip flop variation is the resettable flip flop。

 So a resettable flip flop has clock and D inputs as usual。 And now it has this extra input。

 the reset input。 And here's the symbol reset goes on the bottom or just a small R to indicate a reset input。

 Sometimes these are also called clear input。 C LR inputs。When reset is one。

 the state bit that's being stored in the flip flop should be reset。2，0。So Q is forced to zero。

 not just the output， but what's being stored in that state element。When reset is 0。

 acts like a regular default flip flop and samples D on the rising edge of clock。

NowThere are two types of resettable flip flops。 So there's this synchronous resettable flip flop。

 And that is when reset occurs only at the clock edge。 So the reset input can go high at some time。

But。It waits for the next clock edge。For that reset to take effect for Q to be reset to 0。

Asynchronous reset。Resetable flip flops reset immediately when reset is one。 So when reset is one。

Then Q becomes 0 immediately without waiting for the clock edge。

Asynchronously resetable flip flops require changing the internal circuitry of the flip flop。

 because right if you look at our symbol for our flip flop。We can't change anything。

Unless we get a clock edge， right， we， by definition， we said， well。

 this output Q is only going to change or what state bit's going be stored。

 Q is only going be changed at the rising edge of the clock。

And so in order to build an asynchronously resettable flip plot that responds to reset。Right。

 when reset goes high， then we have to actually dive down into the latches。

 the de latches of the flip flop。 And it turns out we can't even build it at this level， L1， L2。

We actually have to dive down even another level。Inside of。These the。UseD latches。

But a synchronously resettable flip flop， a synchronously resettable flip flop can be built using the same method that we showed for the enable。

 So here's our。😊，Our flip flop， our regular default flop。

And now we want to add the capability for it to be reset at the clock edge。 So synchronous。

So we can say， well， let's see we we could build a similar similar truth table to what we had。

With the enabled flip flop。When reset is。Is 0。 What do we want to fee to D N， Well， it just D。

My reset is one。What do we want to feed to D in， Well， we want to feed in a zero。

And so now we can write an equation for this。We look at this top row， DN。Equals while reset bar。

Reet bar。We said it0， and D。AndThat's how we get a one on D N， because D has to be one。

And reset has to be zero to be in that case。Or。Next row。Reset。And well， what's this。And 0。 Okay。

 well， anything add 0。 right， the only way we can get a one on DN is if we have a reset。B。And D。

 right， this is gonna be 0， no matter what。Okay， so。That's pretty easy。 So here we go。

 We put an and gate。包宝。With reset。B儿。And。And we feed that to D end。 And now we have a synchronously。

Reseable flip flop。 So let's， we could even try it out and say， okay， well。

 what happens when reset is 0。 Well， if reset is 0， we get a 0 bar。 So get one and D。

 So D just passes through。To d end。What happens when reset is one？When reset is one。

We get a one bar right at the other side of this bubble， we get a zero。

0 and something on this end gate。Fororsces DN。To 0。 So that next clock edge。Next rising clock edge。

 we get 0 being stored in our flop。And why is this important。

 why is it important to have a resettable flip flop， Well， like we said in a previous slide。

We turn this。 turn a flip flop on。 We turn our circuit on。 Who knows what state they're in。

 It's important to know to have a fixed state or a known state of our flip flops。Otherwise。

 unknown state Who knows。Hopefully， it works right。 That's not a good way to go。 right。

 I mean to have it in in a known state。And so， here's。Here's a， here's that， that flip flop。

With the resettable feature， the synchronously setable feature。

 And this one shows just reset bar being fed into that and to gate。

We can also have setable flip flops， and this has a set input。

With S on the bottom or set in a larger symbol of this setable flip flop。

 The function is that when set is one。Q。Gets set to one。And when set is0， acts like a regular。F发。

And so how would we build this， Well， again， there are synchronous and asynchronous versions of a setble flip flop。

 This synchronous version， we can start with our regular flip flop and add some circuitry here。

 some combinational logic here。😊，And with the asynchronously setable flip flop， we'd have to again。

 modify the internal nodes of the， of the flip flop。



![](img/b75e559fcc458b3099d0d34663bb31c5_2.png)