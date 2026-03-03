# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P18：Chapter 2 6.Boolean Theorems of Multiple Variables.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， the topic of this video is Boolean algebra， and in particular， theorems of several variables。



![](img/fdb8c82e5ab56ec708738ca30716229f_1.png)

Well， now that we've covered theorems of one variable。

 we'll talk about more interesting theorems involving multiple variables that we can use to simplify boolean equations。

 and we'll also talk about how to prove these there。So theorem 6。Is commutivity。

 This just says that the order doesn't matter。 B And C is the same as B as C and B。Likewise。

 B or C is the same as C or B。 This is just like the regular rules of algebra。 And notice again。

 that every theorem has its duel where we switch and an ort。Also， just like regular algebra。

 Boolean algebra is associative。So B and C， quantity and D is the same as B and quantity， C， And D。

Likewise， for or。The distributive law applies to。 So B and C or D is the same as B， And C or B。

 And D。Unlike regular algebra， it also applies to or。

So B or C And D is the same as B or C and B or D。Covering。

Allows us to eliminate an unnecessary variable and simplify。 So if we have B and B or C。

Then if B is true。This is true。 If B is false， it's false so we can just simplify to be。Likewise。

 B or B and C simplifies to just B。 B covers C。We can do combining。B and C or B And C bar。 Well。

 if C is true， we've got this case。 If C bar is true， C is false， we've got this case。

 So in any case， we've just got B。So we can combine the two terms to just get B。Likewise。For。

And finally， consensus， if we have B and C or B bar and D or C and D。Then by consensus。

 we can reduce it to just the first two terms。Because。Yxi。Is true。Andy is true。

Then either we've got this term or this term。 So we don't need to see Andy。To prove these theorems。

 there are two general methods， one is called perfect induction。

 And this just means try all the possibilities。 Since our variables are just 0 or  one。

 and we have a finite number of them。 It's easy to just try all the possibilities。

Another method is more traditional that you can apply other theorems and axioms to simplify the equation。

So， let's try。The covering theorem。This was that B and B or C is just equal to B。And first。

 let's prove this by perfect induction。So if B is 0 and C is 0， then B or C is 0。

So B and B or C is 0。If B is 0 and C is 1， B or C is 1。But B and of that is 0。If b is 1， C is 0。

 then B or C is 1， B and that。If B is one， C is one， then。B or C is one， And B， And that is one。So。

 now， we show that。This con。Exactly matches this column for all four rows。

So the two must be the same。Q we it。Another more traditional way to prove this is a bit more。TDS。

But we could apply a series of theorems so we could start with B and B or C。

And by the distributive property。We can expand that to B and B， or B， and C。Then， by item， potency。

We can simplify B and B to just B。By the no element， we can expand that back out to B and1。Now。

 applying the dis of property in reverse。We can。We have B and two things， so it's B and1 or C。Next。

 applying the null element，1 or C。Becomes just one。And， finally。By the identity property。

 B and1 is just B。QVD。Here's another example of proving using other theorems to prove the combining theorem。

That B and C or B And not C is just B。We can use the distributed property to simplify this to B and C or C bar。

And then。Apply compliments。 C or C bar is just one。And then the identity， B and1 is just。QV点。

There's one more theorem we'll talk about。 This is the most interesting of the bunch and very useful when we're working with Nns and nors。

The theorem says that not of a bunch of variables and together， not B and C And D。Is equal to the。

Some the at oing together of the complements of the variable。So it's not B or not C or not D。

In other words， the compliment。Of the product。Is the sum of the comp。So。

 the complement of the product。If we take。And and Kate and。Put a knot on the output。That's the same。

Yes。The sum of the compliments in or of inverted input。The dualo。Says the compliment of the sum。

Not of a bunch of os。Is the product。Of the complements and of a bunch of inverted inputs。So。

 the complement of the sun。Is equal to the product。Of the compliments。So once upon a time。

 a digital design student was learning about this stuff。

 and it was just making them dizzy and giving them headaches。And they went to the doctor。

 and they said， doctor， doctor， all these sums and products and compliments are giving me a headache。

And the doctor said。Well。Take。嗯。Don't take this pill。And don't take that pill。Or equivalently。

 take neither this pill nor that pill。And call me into Mar。



![](img/fdb8c82e5ab56ec708738ca30716229f_3.png)

All right。 So to recap， we have these theorems of several variables。 Booleing algebra is commutative。

 It's associative。And it's distributive， just like regular algebra。 There's covering。

 combining and consensus that allow us to simplify。

 And the Morgan's law lets us work converting things between nas and Nors。

