# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P15：Chapter 2 3.Boolean Equations SOP and POS Forms.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Any questionss。

![](img/96049db365d7b9330df90621cd08aa3d_1.png)

So blueing equations are a very helpful way to provide the functional specification for a block of logic。

 They describe how the outputs depend on terms of the input。For example， in this block。

We have three inputs。And named A， B and Cid。And two outputs named S And C out。And。

Each of the two outputs is a Boolean function of the three inputs。So for example。

We could say that S is a exclusive or B exclusive or Carion。

And C out is A and B or A and C in or B and C in。 That would be a functional specification described if Boolean equations。

Let's provide some definitions that will be helpful here。First of all。

 a complement is a variable with a bar over it。So if A， B and C were our variables， an A bar。

 B bar and C bar would be their compliments。Next， a literal。Is either the variable or its complement。

 So in this case， there's 6。Literals， A， A bar， B， B， bar and C， C bar。

An implicant is a product of literals。 In other words， the and of literals。

So AB C bar is an implicant because it's a product of some of the literals。

Ay bar C is another implicant。BC is an implicant。B bar。Would be an implicate。

A midterm is a product that includes all of the input variables。

 either in true or complementary form。So A B C bar is a midterm because it has A has B。

 and it has C bar。All of these are midterms。But， for instance， B。

 C is not a mid termm because it doesn't involve a or A bar。Finally， max term is a sum。

 In other words， an or of。Literals。That includes all of the input variables。

So A or B bar or C is a max term。A bar or B bar or C is a max term because they include all three variables。

But。B bar or C is not。A max term， because it doesn't involve A or A bar。We can write any。

Boleing equation in some of product forms。And in this form， we're going to use sum of the minterms。

So a midterm is the product of the literals。And in a truth table。

 we can associate each row of the truth table with a minter。So， for example， in this truth table。

 the first row A 0， B 0 corresponds to a interim A bar， B bar。

And that midterm is true when we're on this row。The second row，0，1。Has a Min term of A bar B。

 because A is 0 and B is one where on this row。The third row， A 1 B0 has them inter of A B bar。

And the fourth row， A1， B1 has a midterm， A B。Now， suppose we had a truth table with this particular pattern of why。

Then to find a boolean equation in some of products form。We simply circle the rows。

And which Why is true。And we read off those min termss。 So why is true on row 1 and row 3。

And those min termss are A， bar， B。Or A B。So we have a sum of products equation for this Boolean function。

 Y equals a bar B or A B。And if you look at this， you could probably realize it simplifies to be。

 And later， we'll talk about systematic ways of doing that simplification。

Any truthth table can also be described in some of products form。Sorry。But to do that again。

Any Boolean equation can also be described in product of sums form。Where we have an and of max terms。

So for every row， we can give a max term saying when you're not on that row。So when we're on the row。

0， zero。The max term corresponding to it is A， B。Because。If A is true or B is true。

 we're not on this row。Similarly， when a next row 0，1， the max term is a。Or be bar。

Because if A is true or B is false， we're not on this row。When a is 1， B is 0。

 the max term is a bar B， because we're not on this row in that case。 And finally。When A is1， B is 1。

 the max term would be A bar or B bar， saying we're not on the row in。A is 0， or if B is 0。Next。

We're going to circle all of the rows。That have zeros。In the output。

And well say our output is true if we're not on any of those rows。 So the first row。

Had a max term of A B。That's this row。The third row。Had a max term of A bar B。

So we're not on either row。This max term。 and this max term。

So this is an equation for y as a product of sum。A product of sums， to me。

 is less intuitive way to think about things。 typicallyypically。 it's not how I talk about circuits。

 So usually well work with some of products。Let's do an example。

 Suppose that we wanted to go to the cafeteria for lunch。

 and we're trying to figure out if we're going to eat lunch。 and we need a。

Circuit to help us to side back。So we'll look at the cafeteria if it's not clean or if they're only serving meat well。

 we're going to skip lunch。Let's make a truth table。

So if the cafeteria is not clean and there's no meat loaf。

 we're not having lunch because we don't like it clean。You wanna click。They is not clean。

 And they serving meat loaf， No way。If it's clean and they're not serving meat loaf。Then。

 we will have lunch。But unfortunately， if it's clean and all they have is meat loaf。

 no lunch for rice。So here we've got a truth table。For our silk。Now。

 let's come up with a Booleing equation。 First， let's look at some of products form。

 So this one is fairly easy。 We circle the only row that has a one on it。And he。

Is chewing to this next term， if C。And not him。We eat lunch if it's clean and there's no meatlo。

For product of sums， we would have to circle all the rows where the output is 0。And we could say。

 we would eat lunch。If it's clean。Or they're having meatloaf。And。Hs。Not clean。

Or they're having meat love。And。It's not clean。Hu。They're not having me love。

So if all three of those are true， then we'll eat lunch。And as you see， that might be less intuitive。

Let's do some examples of forming Boolean equations from word problems。

So usually you can do this by just looking at the problem and taking the plain English and it often translates straight into Boolean。

So for example， let's say we'll go to the park if it's not raining and we have sandwiches。I can say。

 park。Equals not raining。And sandwiches。That's say you're going to be a winner if we send you a million dollars or a small not pad。

So winner is million dollars or notepadd。Suppose you could eat delicious food if you either make it yourself or you have a personal chef。

 and he's talented， but not expensive。So you eat the delicious food。 if you make it yourself poor。

You have that personal chef who is talented， but not expensive。

Say you can enter the building if you have a hat and shoes on or if you just have a hat on。

E equalals H and S or。Now， suppose you could enter the building if you have a hat and shoes on or if you have a hat and no shoes。

That would be E equals H。S。

![](img/96049db365d7b9330df90621cd08aa3d_3.png)

4 H， no shoes。