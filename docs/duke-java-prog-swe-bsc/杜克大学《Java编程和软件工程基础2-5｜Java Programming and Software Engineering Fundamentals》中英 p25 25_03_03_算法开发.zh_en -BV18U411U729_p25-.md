# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p25 25_03_03_算法开发.zh_en -BV18U411U729_p25-

![](img/538f8ff7664e5bbaaadbc39af3654bde_0.png)

Hello and welcome back， you are going to be working with strings that represent DNA。

 solving problems like searching for genes in them。

This problem is a great one to learn on because even though we're going to start with a greatly simplified version of it。

 it's an important problem with real world applications。



![](img/538f8ff7664e5bbaaadbc39af3654bde_2.png)

Of course， the lessons you will learn about working with strings and programming in general will help you far beyond this problem domain。

 whatever sorts of problems you want to solve， strings are likely to come up in them in one way or another。

 HTML， email， or really anything that is text that is represented as a string。

You are also going to learn some other important lessons as you work on these problems。

 like how to do math and Java。Of course， math is also ubiquitous in programming since everything is a number。

 and perhaps most importantly， you will get more practice developing and implementing algorithms with the seven steps。

Before we dive into DNA related problems， we need to give you a bit of domain knowledge。

 some terms and concepts related to working with DNA。

Here is a string that could represent some piece of DNA。

 you will see that it's made up of four letters， A， T， C， and G。

Each of these represents one nucleotide， which are the basic building blocks of DNA。

Three nucleotides together make a codon。Which each describe one amino acid。

The ATG codon shown here is special in that it indicates the start of a gene， accordingly。

 it's called the start codon。And the TAA codon is also special in that it indicates the end of a gene。

 so it's called the stop codon。There are a couple other stop codons， but for now。

 we're only going to think about TAA。Everything between and including these two codons makes up one gene。

The first problem you're going to work on is finding a gene in a string which represents DNA。

That is you want to write a program which takes a string like this one and gives you all the text between it and including the start code on ATG and the stop code on TAA。

You're going to start with a greatly simplified version of this problem。

Just finding those letters and all the text between them。

You will not worry about the fact that real genes must be multiples of three in length because they're made up of codons。

Or that there are some other stop codons or a few other complexities to start with。

As you master more string and algorithm concepts， you'll add features to your program。

 making it more realistic with each step。As always。

 the first thing you want to do is work on an instance of the problem yourself。

Let's take this DNA sequence and find the first gene in it。Let's find the start co on， aha。

 there it is。Now let's start looking after it to find the stop codon and we find it right here。

That means that we want to take all this text representing the nucleotides in this region。

As our answer， the gene that we found。Now that we have worked an example。

 we should write down what we just did。First。I found the first occurrence of ATG。

Then I started looking after the ATG for TAA。Last， I took all the letters between and including them as my answer。

 A G， ATT， TTC， etc cetera， all the way to TAA。Okay。

 now that we wrote down what we did for that specific problem， we want to generalize it。

Why did we look for A G。We always want to look for it， that's the start codon。

What about TAA after ATG？We always want to do that， too。 that is the stop codon。

And taking all the letters between and including them。We always want to do that too。

The only thing that isn't really general here is the specific string we wrote down as our answer。

 which was more of a descriptive note to ourselves than anything else。

Now that we have a general algorithm， we'd like to turn it into code。

But we need to learn some new Java concepts first。How do we find ATG in a string？For that matter。

 how do we even represent or talk about the position of something in a string？



![](img/538f8ff7664e5bbaaadbc39af3654bde_4.png)

And how would we get all the letters in a particular range in a string？



![](img/538f8ff7664e5bbaaadbc39af3654bde_6.png)

You'll learn about these concepts， then you'll be ready to turn this algorithm into code， thank you。



![](img/538f8ff7664e5bbaaadbc39af3654bde_8.png)