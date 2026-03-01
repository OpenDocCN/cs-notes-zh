# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p37 37_03_09_逻辑与或运算.zh_en -BV18U411U729_p37-

![](img/3bc2e5a40efe1b2722771aa9537fc050_0.png)

Okay， now you have an algorithm which works with any of the three stop codons， however。

 let's explore how you could make this code work if we decided to have fine stop codon return at negative one when there's no valid stop codon rather than the length of the string。

Note that this is a perfectly valid design choice and mirrors what the dot index of method does。

 but we need to learn a new concept to make it work with our code。

 You'd want to change line 6 of the gene finding algorithm to reflect this choice。

 You cannot just take the minimum。 Since negative one is smaller than any valid index。

 So what you want to do is pick the smallest number that's not negative one。

 Let's look at a few examples。Here， TAA index is negative 1， and TGA index is 3， and TA G index is 6。

 What index should you pick for the stop co on。Well， we want three because it's the smallest number。

 which is not negative one。 notice we can't just pick the minimum1 because that would give us negative one。

 which is not a valid value here。What if we had five， negative one， and eight， we'd want five。

Likewise， with 10，4 and negative 1， we'd want four。And with1， negative 1 and 11， we'd want 11。

Let's think about how we can express this decision process algorithmically。In the first example。

 we compared these two numbers first。Even if you think you're comparing all three at once。

 you're really comparing two at a time， very quickly and perhaps without thinking about what you're doing。

😡，Of these two values， we prefer three， since the alternative is negative one。

And then we compare three against six， we choose three since it's smaller than six。

In the second example， we'd compare5 to negative1。Then we choose five。And compare this against eight。

In this choice， you'd pick the smaller， which is five。In the third example。

 you'd compare 10 against four。You choose four because it's smaller。

And then you'd compare four against negative1。And choose4。In the final example。

 you're comparing negative1 against negative1。It doesn't really matter which you pick。

 they're the same。You then compare negative 1 against 11。And you choose 11。

Note you should think about what you would do if all three values were negative。

 what would that mean， it would mean that no valid stop codon exists。

 we'll have to use that in our code。😡。

![](img/3bc2e5a40efe1b2722771aa9537fc050_2.png)

Now how do we think through how we made these choices？

We're only going to look at the logic involved in making the choice between one pair。

That same logic will work with the second choice。In the first example。

 we picked TGA indexex because TAA index was negative1。In the second example。

 we picked TAA index because TGA index was negative one。

In the third example where neither is negative1， we picked TGA index because it's smaller than TAA index。

 and in the final example， it didn't matter which we picked since both were negative one。

Let's write down what our logic is for making that selection。If TAA index is negative 1。



![](img/3bc2e5a40efe1b2722771aa9537fc050_4.png)

We'd want to pick TGA index。But that's not all there is to it。

We'd also choose TGA index if both TGA index is different to negative one and TGA index is less than TAA index。

 notice how we've expressed this logic with or and and logical connects。

 which let us make complex conditionals out of simple ones。

Now let's put that logic into the algorithm we're working on。

We'll use that logic to pick between TAA index and TGA index and we'll store the best choice there is in a variable called Min indexex。

 then we'll choose the same logic to choose between Min indexex and TAG index。

If min index is negative 1， there were no valid stop codons， so we'll give back the empty string。

Otherwise， we've found a gene。Now let's see how we express these or's and ands in Java。

You can express and with two ampersands。This is a shift7 on most US keyboards。

 we can see in this example if x is less than y and y is less than z。

You can express or with two vertical bars also called pipes on most US keyboards。

 this symbol is shift backslash and we can see an example here。If A is greater than B。

 or C is less than D。In the particular case of the algorithm we're working on。

 you could express the step as shown here。Notice how the or corresponds to the two vertical bars。

And the and corresponds to the two ampers sands。And and or have special rules called short circuit evaluation。

Which basically means that if Java can figure out the result of an entire expression involving and and ore。

By evaluating only the first operaand。Then Java will skip evaluating the second operaand。

Let's look at an example。Suppose x is8 and y is1。X is less than y。

Is not true because eight is not less than one。So X less than y evaluates to false。

 there's no reason to evaluate y less than Z， because whether it's true or false。

 the whole and expression will be false because false and anything is false。For or。

 consider this example and suppose a is3 and B is1。Here。

 A is greater than B is true because3 is greater than one。So the whole or expression will be true。

 regardless of whether C is less than D or not。

![](img/3bc2e5a40efe1b2722771aa9537fc050_6.png)

So there's no point in evaluating the expression C less than D， because true or anything is true。

Why is short circuit evaluation important？If you skip evaluating Y less than z in this example。

 it doesn't really matter so much。But it's much more useful when the second opera end could crash your program if it's evaluated。

 For example， here we're checking if x is less than the length of a string。And。

That the character at the X index of the string is the letter A。



![](img/3bc2e5a40efe1b2722771aa9537fc050_8.png)

If the first condition is false。Then x is not a valid index， it's beyond the end of the string。

So trying to get the X character with the dot carat method would crash the program with a string index out of bounds exception。

 But fortunately， this line of code is safe because of short circuit evaluation。

 the dot carat method will never be called when x is greater than or equal to the length of the string。

Relying on short circuit evaluation is a great example of defensive programming and one of the tools in your Java programming toolkit。

Have fun。😊。