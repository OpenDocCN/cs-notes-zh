# 【计算机体系结构】普林斯顿—中英字幕 p71 70_05_vector-parallelism -BV1ii421D7WR_p71-

![](img/83d91d7955c7d7d682cf8b47fc6527b3_0.png)

Okay， so now we gets into some more fun pictures here。 So let's take a look at。😊。

A processor based on。The in order processors we've been looking at up to this point。We fetch tocode。

 We added or rename some stage here， which we'll talk about in a second。

 And then we have different pipelines。And one right back。We have two register files。

 We have the Scour register file， which is what we were calling our old register file。

And we have the vector register file。Which has lots and lots of data in it。

The vector length register sort of sits out in front here。In our register fetch stage。

And we make a special stage for this because it does a lot of work。What is it going to do。

When an operation gets to the stage， it's going to start。Reading。The register file。

And if you have vector register， it's going to sit there and read the first element。

 the second element， the third element in time。And start shoving it down one of the pipes。

 So let's say this is our multiply pipe here。It's four stages long， and we do a multiply。

Of 60 with a vector length of 64， it's gonna sense。

 it's gonna do 64 sequential reads out of here and then 6， send 64 instructions down。

This multily pipe。Note， we are not looking at any perilism yet in this example。

We are doing everything sequentially here。 One thing you will note is instructions can stop here。

 and they basically generate more， more work at that point。And and up to the vector。

 maximum vector length to whatever the vector length register is currently set at。

So let's look at a basic operation here。We're gonna have a piece of code。

 which is doing the same operation。 We're taking。Vector A and vector B。

 and element Y is multiplying them。And I is four。I use a small eye here because it's hard to draw these things with I of 64。

 Thiss lots of instructions to draw。If we go look at the assembly code。

 it's the same assembly code we had before， but we load the vector length with 4 instead of 64。

So load vector， load vector， multiply vector vector， double and。Store。Let's look at the second load。

 multiply and store。 I don't have the second load or the load to meet on here because it just took up too much space。

This load vector here it's gonna start off。 It's going fetch decode。

 And then it's gonna sit at the R stage for a while。Inserting loads， loads， loads。

 loads down the pipeline。Okay。This basic vector execution， we don't have any bypassing。And we do。

Register。Depenency checking。On the。Through the register file and on a whole register。

 So we install an instruction if the whole vector is not ready。Now。

We're going to look at ways to get that better in a second。

 But what that means is we wait for all of the values of this load to right back to the register file before we go and start to do the register fetches of the next instruction。

Then we do the multiplies。 Multiplies have longer pipeline lengths。

We wait for all of those multiplies to write to the register file before we start to go do。

The stores， operations。So our scoreboarding here is very。

Our our scoreboarding and our bypassing here are very， very limited。

 you could have basically check to make sure everything is in the register file before before you go ahead。

I did want to introduce one piece of nomenclature。And your book calls this out。It's called a chime。

So a chime is how long it takes to execute。One vector instruction。An。The architecture。

So what we're going see a little bit is we're gonna to have some architectures where you can actually。

Overlaap。Some portion of the execution。Let's say by having different functional units and decrease the chi。

 So for this architecture here， the chi is， is 4 because it takes basically occupancy of four4 vector length of of4。

And we only have one A U effectively， that can be used at a time here。

So now let's take a look at how to， how to make things run a little bit faster。

 We explore no perilism。 The only real advantage we've taken advantage of here is we've decreased our memory bandwidth。

 We've not actually。decreased our instruction， fetch and instruction fetch memory bandwidth。

 But that's not a real great reason to go do anything。 that probably reduces power a little bit。

But we wouldn't go fast。So we can start to think about how to overlap。If we， if we have different。

Functional units。X 0， the load， the A U， the load， the store and the multip unit。

We can start to think about overlapping them。In both space。And time。

So here's an example where we're executing。32 elements。Is our vector length。

And we actually have multiple copies of the functional units。And we have multiple function units。

 So we can overlap。Different executions with each other。

 And we'll look at some more detailed examples in a second。

So we can start to add perilism by using multiple units at the same time。Our adder unit。

 our multi unit， our load unit， which was， this was L。 And this was our Y， and this was our X units。

And we could actually put multiple copies of those。And well we're going to call those lanes。



![](img/83d91d7955c7d7d682cf8b47fc6527b3_2.png)

![](img/83d91d7955c7d7d682cf8b47fc6527b3_3.png)