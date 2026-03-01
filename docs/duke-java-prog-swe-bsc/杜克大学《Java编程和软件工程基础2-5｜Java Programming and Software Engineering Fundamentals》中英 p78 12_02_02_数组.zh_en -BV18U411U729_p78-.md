# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p78 12_02_02_数组.zh_en -BV18U411U729_p78-

![](img/9642db8f70eef95c2a73768431a82caa_0.png)

Hello。😊，You're going to learn the basics of a powerful programming construct， the array。

 nearly every programming language in widespread use uses a similar structure to be able to represent many items with one variable。

When you wrote code to help a genome scientist solve a problem。

 you could count the number of occurrences of each C， G， T and A in a strand of DNA。



![](img/9642db8f70eef95c2a73768431a82caa_2.png)

![](img/9642db8f70eef95c2a73768431a82caa_3.png)

This is a real problem that helps find protein coding regions rich in CG content。



![](img/9642db8f70eef95c2a73768431a82caa_5.png)

As a programmer learning about encryption and decryption。

 you'll need to count the number of occurrences of A， B， C。

 and every letter of the alphabet through X， Y， and Z， 26 counters。

To be able to break a Caesar cipher or decrypt a message encrypted with a Caesar cipher。

Although you could do this with 26 variables， you'll learn a new concept to help with the coding。

 You'll learn about arrays which are homogeneous collections of values。

 Here you see post office mail boxes。 They each look the same， but each is numbered differently。

 You can access box number 344， or box 345， and you can either store letters and packages in a box。

 or take them out of a box。Arays are similar concepts in programming， as you'll see。

 one array could represent 26 or 1026 counters if your alphabet was huge or if you were solving a different problem。

Let's look at code to help a genomic scientist。We'll look at code that counts occurrences of C， G， T。

 and A。To understand and motivate the problem of counting 26 letters。



![](img/9642db8f70eef95c2a73768431a82caa_7.png)

As you can see， we've created four counters， initialized each one to zero。

And then incremented the appropriate counter as we process every nucleotide in a digital strand of DNA。



![](img/9642db8f70eef95c2a73768431a82caa_9.png)

This solution works， but its very hard to scale to having 26 counters。

 which you would need to count every letter A through Z as part of decrypting a message encrypted using a Caesar cipher。



![](img/9642db8f70eef95c2a73768431a82caa_11.png)

This isn't conceptually hard。 We could use C A， C， B， C， and so on up through variables。

 C Y and C Z to have 26 variables， and we could have 26 if statements to increment the appropriate variable。

 but writing the code and changing what we do with 26 values is time consuming and difficult to change if we want to print something different。

 for example， when looking at the output。

![](img/9642db8f70eef95c2a73768431a82caa_13.png)

We'll use an array， an indexed collection to use one variable in place of 26 We'll break the Caesar cipher by counting occurrences of each character in an encrypted message。

 a message in English would typically have the letter E as the most frequently occurring character。

 so once we found how many times each character occurs in an encrypted message。

 It's likely that this character is E， and we can determine the shift using used in encrypting the message。

 making the decryption process easy。

![](img/9642db8f70eef95c2a73768431a82caa_15.png)

In general， counting and collecting values is an important tool in writing programs。

 so learning about arrays in the context of breaking a Caesar cipher will help in solving many other problems。

 you've seen the class storage resource which was helpful in storing string values that class was useful but its use was limited。

 will expand on the idea of arrays and the storage resource class later for now we need an indexed collection like the collection of mailbox we saw in which a number used to access a specific location。



![](img/9642db8f70eef95c2a73768431a82caa_17.png)

![](img/9642db8f70eef95c2a73768431a82caa_18.png)

![](img/9642db8f70eef95c2a73768431a82caa_19.png)

This is the same concept you've seen with strings in which an index is used to access a particular character in a string using the dot Careat or dot substring methods。

 as can store any type of value， not just the type care that's used in strings。

We'll look at the concepts and code in using arrays and see how they're similar to what you've seen before with strings。

You define an array similarly to defining a string。



![](img/9642db8f70eef95c2a73768431a82caa_21.png)

When defining a string variable， as you see here， you indicate the characters that are in the string and assign these characters to a variable。



![](img/9642db8f70eef95c2a73768431a82caa_23.png)

![](img/9642db8f70eef95c2a73768431a82caa_24.png)

With an array， you must specify how many storage locations there are and use the square brackets with a variable name to indicate the variable is an array。



![](img/9642db8f70eef95c2a73768431a82caa_26.png)

This code allocates 256 memory locations， each one holding an int with a value 0。



![](img/9642db8f70eef95c2a73768431a82caa_28.png)

Which is the default value for integers in an array。



![](img/9642db8f70eef95c2a73768431a82caa_30.png)

The concept of indexing is used to access elements of a string。And an array。

With a string that that carat method is used with an index to access a specific character。

 The first character is 0 because we use0 based indexing。



![](img/9642db8f70eef95c2a73768431a82caa_32.png)

With as， the bracket operator。Access is a specific element again with zero based indexing。



![](img/9642db8f70eef95c2a73768431a82caa_34.png)

When writing code， you often need to know the number of characters in a string or the number of elements in an array。

With the string， you use the dot length method to determine how many characters there are in the string。

With an array， you use the value stored in。Dot length to access the number of storage locations allocated for the array。

 Note that dot length is not a method for arrays。 This is sometimes a source of confusion。

 when writing code。We'll look at the code to count the number of occurrences of every character A through Z。



![](img/9642db8f70eef95c2a73768431a82caa_36.png)

You'll see this code and the concepts in it will help you solve many problems when programming。



![](img/9642db8f70eef95c2a73768431a82caa_38.png)

In this code， you'll see a variable named counters that will represent 26 different counters。

The code will store the number of occurrences of a encounters sub0。

 We use sub as a shorthand for subscript， a term coming from mathematics。



![](img/9642db8f70eef95c2a73768431a82caa_40.png)

We'll see that counter sub K is the number of occurrences of the case letter。



![](img/9642db8f70eef95c2a73768431a82caa_42.png)

By this， we mean that the number of B's is at counter sub1。

And the number of Z's is at counters sub 25。

![](img/9642db8f70eef95c2a73768431a82caa_44.png)

As you look at the code， you'll see there are three parts。

Just as there were with a code that counted the number of occurrences of CG。

 A and T in the stream representing DNA。In that code。

 four counters were defined and initialized to zero。

Here there are 26 counters defined and initialized to 0。The array， referenced by variable counters。

Takes the place of 26 different variables。In the DNA counting code。

 we used a sequence of four if statements to determine which counter to increment。

Here we use the location of a character in the string alpha。

As the index of the appropriate counter to increment。Note that A has indexed zero。

We even use both upper and lowercase A's using the character do2 lowercase method so that the index value returned by Allf dot index of helps us increment the appropriate storage location in the counters array。

Finally， to print each result， we use the loop index K to both access the case value stored in Alf。

And the case value stored in the counter's array。You'll gain experience in solving problems with arrayray。

 Here's a quick summary of what we've just introduced。



![](img/9642db8f70eef95c2a73768431a82caa_46.png)

Arays are indexed collections of values。

![](img/9642db8f70eef95c2a73768431a82caa_48.png)

When defining an array， you will typically provide an integer value indicating how many elements can be stored in the array。

 It's possible to define a variable like x， as you see here， with no storage allocated for it。

 simply to define the type of the variable。 This could be useful， for example。

 as a parameter in the method。

![](img/9642db8f70eef95c2a73768431a82caa_50.png)

![](img/9642db8f70eef95c2a73768431a82caa_51.png)

![](img/9642db8f70eef95c2a73768431a82caa_52.png)

If you define an array by calling new， you must provide an integer value for the number of array elements。

In an in array， all locations will be initialized to zero。



![](img/9642db8f70eef95c2a73768431a82caa_54.png)

For a string array， all array locations are initialized to know。

 That's the valueve seen before that indicates there is no object being referenced。



![](img/9642db8f70eef95c2a73768431a82caa_56.png)

Array locations are read and written using indexes。You can store a value in an array， as shown here。

With S sub3 getting the string hello， this is writing a value into an array location。

You can also access or read an array location as shown here。



![](img/9642db8f70eef95c2a73768431a82caa_58.png)

Where on the right hand side of the assignment statement。

 we see x sub 3 is used to assign or write to a value on the left hand side of the assignment statement。

 x sub2。

![](img/9642db8f70eef95c2a73768431a82caa_60.png)

Once the storage is allocated for an array， the array size does not change。

 This may be why dot length is not a method， but a value。



![](img/9642db8f70eef95c2a73768431a82caa_62.png)

When an array is passed to a method， the contents of the locations referenced by the array can change。

This is subtle， and you'll see examples of it when we use arrays to solve problems。 have fun coding。

