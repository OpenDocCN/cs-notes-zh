# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p28 28_03_06_Java数学运算.zh_en -BV18U411U729_p28-

![](img/ff99254d88d28961aa155b3cc7c3ff6d_0.png)

All right， now you have an implementation of the rather oversimplified version of this program。

 it just looks for ATG and then TAA and gives back everything in between。

But real genes have to be a multiple of three in length since they're made of codons。

 each of which is three nucleots long。For example， this string is a valid gene。

You can see here how it can be divided into codon starting with ATG and ending with TAA。However。

 this string is not valid。Even though it has ATG。And it has TAA。When we look between them。

 we don't find a valid sequence of codons。

![](img/ff99254d88d28961aa155b3cc7c3ff6d_2.png)

Now， let's make our algorithm a little bit more realistic。

 You will fix this aspect of your algorithm。It will still be a simplification。

 but a bit more realistic。 At this point， it's really good to note that starting with the simple version and adding features is not only a useful technique for you as you learn new concepts。

 it lets us introduce a few concepts at a time， but also important when writing real， large。

 complex problems。😊，Okay， so you just saw two examples of DNA strengths。

One that has a valid gene and one that does not。How can you tell in general。

 what is the change you need to make to your algorithm？



![](img/ff99254d88d28961aa155b3cc7c3ff6d_4.png)

It might be useful to show the indices， as we have shown here。

And highlight the location of the start and stop codons。

Do you see how to algorithmically tell the difference， If not， that's fine。

 It can be hard to spot patterns， but you will get better at it with practice。

One great technique to find patterns is to make a table。

You might remember that we did this in some of our examples。



![](img/ff99254d88d28961aa155b3cc7c3ff6d_6.png)

We can then add more examples to our table， as I'm showing here， to help us see the pattern。

 some with yes， answers and some with no answers。Maybe you see the pattern now。

 or maybe it is still hard to see。What can you do if the pattern still isn't clear？

Maybe adding more rows will help or maybe not。Instead。

 we might start exploring the relationships between the items in the table here we have added another column for the difference in the index of the stop codon and the index of the start codon。

The ones that have yes answers have differences of6 and 12。

And the ones that have no answers have differences of 4 and 11。

What do 12 and6 have in common that 11 and 4 do not？We might be able to think of a lot of things。

6 and 12 were both multiples of6， but that doesn't make sense in the context of this problem。

 If we did more examples， we could find ones with yes answers that have 3 or 9 or 15。However。

6 and 12， as well as 3，9 and 15， are all multiples of three。 This relationship does make sense。

 as we know that the length must be a multiple of three。



![](img/ff99254d88d28961aa155b3cc7c3ff6d_8.png)

Nown that you know the relationship you know that you want to look for。

 you need to do some math and Java。YouYou need a way to ask if the difference between two numbers is a multiple of three。

If you took course one with us， you might remember the mod operator。

 which gives you the remainder when you do division X mod y written x per sine y means divide by divide x by y。

 but give me the remainder， not the quotient。 This can help you with the problem at hand。

 since a number that is a multiple of3 has a remainder of0 when divided by 3。

 That is if x mod 3 is equal to 0， then x is a multiple of3。

You can use other mathematical operators in Java plus minus times divide， they're all valid。

You can also use equals equals to see if two numbers are the same。

 not equals to see if they're different， and less than， less than or equals。

 greater than or greater than or equals to check for inequalities。

You can also combine simpler expressions into more complex expressions。

 This expression checks if a minus B mod 3 is equal to 0。

It is evaluated by first evaluating a minus B。Then taking that result and doing modd 3 on it。

Then finally， taking that result and checking if it's equal to zero。

This is pretty much exactly what you need for the problem at hand to see if the difference between two things is a multiple of three。

While you are learning about math and Java， there are several different types of numbers。 Actually。

 there are some variations on these， but you don't need to worry about that right now。

One type of number is int， which represents integer numbers like negative 2， negative 1，0，1，2。

 etc cetera。 ints can't have a fractional part。The other type is double。

 which represents real numbers， ones with fractional parts like 1。2 or 3。457。Of course。

 you could also represent 3， which is 3。0 with a double。

 You only want to use doubles when you need to， since they have some behaviors。

 that can be really confusing to novice programmers。One word of caution about integers， however。

 is that math on integers always yields integers。So what do you get if you divide5 by 2？

If you're thinking 2。5， remember that you can only get an integer result so you get two。

What about 100 divided by 3 times 4？You will get 132 since 100 divided by 3 is 33。

And 33 times 4 is 132。So what if you do 100 times 4 divided by 3。

 See like you should get the same answer， right？ Well， actually， now you get 133。

 Why100 times 4 is 400 and 400 divided by 3 is 133。

 These sorts of issues should not come up in these courses。

 but are good to be wary of if you're doing in your division。

Another thing to know about math and Java is that it has order of operations， rules like math。

In programmer Sp， these rules are called precedence and Associivity。As with math。

 A plus B times C means to do B times C first， then add that result to A。What if you have mod。

 it has the same precedence as division， meaning it takes place at the same place in the order of operations。

 So a minus B mod 3 means to do B mod3。Then subtract that result from a。

 This is why we put parentheses around a minus B earlier when we wanted to do the minus first。

 then take its result mod 3。Comparisons for equality happen very late in the order of operations。

 A plus Bs C minus D means to first do a plus B， then do c minus D and finally compare the two results to see if they are equal to each other。

These rules are typically like they are in math， multiplication and division come first。

 then addition and subtraction。

![](img/ff99254d88d28961aa155b3cc7c3ff6d_10.png)

Also like maths， you can use parentheses to group things so that they come first。

If you aren't sure what order things will happen， you can always use parentheses to be explicit and be sure you get what you want。

Okay， now that you know about math and Java， it's time to go improve your gene finding algorithm。

Thank you。😊。