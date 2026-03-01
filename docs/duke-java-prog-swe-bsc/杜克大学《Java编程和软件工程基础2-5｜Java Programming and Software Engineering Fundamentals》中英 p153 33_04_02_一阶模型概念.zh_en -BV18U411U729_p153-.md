# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p153 33_04_02_一阶模型概念.zh_en -BV18U411U729_p153-

![](img/0998c148a2e7848aa95b1c4a4066d078_0.png)

We're going to develop the concepts you'll use in implementing the Markov word1 class for generating text based on using one word to predict the next word。



![](img/0998c148a2e7848aa95b1c4a4066d078_2.png)

![](img/0998c148a2e7848aa95b1c4a4066d078_3.png)

We'll use the same concepts we used in the Markov program that generated random text using characters。



![](img/0998c148a2e7848aa95b1c4a4066d078_5.png)

We developed and tested the I Markov model interface， and we'll continue to use that。

 usingsing already tested code is a great idea when that's possible。 If we have a good design。

 the client programs we developed， like Markov Runner， will continue to work。

 even with a completely new model for generating text， one based on words rather than characters。😊。



![](img/0998c148a2e7848aa95b1c4a4066d078_7.png)

![](img/0998c148a2e7848aa95b1c4a4066d078_8.png)

![](img/0998c148a2e7848aa95b1c4a4066d078_9.png)

![](img/0998c148a2e7848aa95b1c4a4066d078_10.png)

![](img/0998c148a2e7848aa95b1c4a4066d078_11.png)

With a good design， the implementation changes， but the interface。

 including client programs that use the interface， don't change。 This is abstraction， at its best。

We are able to reuse client programs because the programs rely on a class's interface and not its implementation。

We will change the instance variable My text to be a string array rather than a string。

 This will require modifying some code。We'll search for words rather than characters， As we'll see。

 this means will need to modify the helper method， get follows and implement some new private helper methods。

Designing classes typically means thinking about a class's state and its behavior。

 instance variables and methods。

![](img/0998c148a2e7848aa95b1c4a4066d078_13.png)

![](img/0998c148a2e7848aa95b1c4a4066d078_14.png)

We'll use the tested design and code in Markov 1 as the basis for Markov word 1。



![](img/0998c148a2e7848aa95b1c4a4066d078_16.png)

Both implement the I Markov model interface。

![](img/0998c148a2e7848aa95b1c4a4066d078_18.png)

Meaning both will have the methods set training and get random text。



![](img/0998c148a2e7848aa95b1c4a4066d078_20.png)

We'll see that in Markov word 1， we search through an array of words。

 which is the training text that's similar to searching a string for a character。

 and a string uses an array of characters in its implementation。



![](img/0998c148a2e7848aa95b1c4a4066d078_22.png)

Will build the random text to return one word at a time。

This is nearly the same as building the text1 character at a time with one small difference。

 We'll need to add spaces between the words。 When building text  one character at a time。

 we use the fact that a space is a character， so spaces were generated randomly。

Let's look at initializing a Markov word1 object。

![](img/0998c148a2e7848aa95b1c4a4066d078_24.png)

We'll need to create and initialize the instance variables。

We store a random object and an array of words as instance variables。

 This is nearly identical to Markov one， but we use an array of strings rather than a single string。

We initialized the fields in the constructor， creating the random number generator。

The instance variable， my text is assigned of value when the method set training is called。

 just like the code in Markov1。Here we use the string method dot split to break a string into words using the regular expression slash slash S plus。

 which represents one or more occurrences of any white space character。

We've used this same idiom before to break a string into words。Now we turn to get random text。

 The second method required by the I Markov model interface。



![](img/0998c148a2e7848aa95b1c4a4066d078_26.png)

The interface requires that we implement this method to return randomly generated text。

The method signature in the interface uses an int parameter named numb cars。

Because in the Markov classes， we designed and implemented the Get random text method that returned a string based on generating a specified number of characters at random。

In Java， a method signature depends on the type of the parameters， not the parameter names。

 so in Markov word 1， we can change the name of the parameter to numb words。

 since we're generating text a word at a time rather than a character at a time。

We add one word at a time to the string builder， which is shown here with the initial key chosen at random。

We also must explicitly add a space between each word。

 So we append a string after each word that's added to the string builder。

This means there's an extra space at the end， but we can remove this with the strings dot trim method。

Were almost done with the get random text method in Markkov word 1。

 The forlo we didn't show on the previous slide is shown here。

 It's nearly identical to the forlo in Markov 1。

![](img/0998c148a2e7848aa95b1c4a4066d078_28.png)

We changed numb cars from the method， from that method to the name numb words used in this version of the get random text。

We also explicitly add a space after the word appended to the string builder。Otherwise。

 the code is identical。We're ready to code and test Markov word 1。

 We'll copy the get follows private method here from Markov1。



![](img/0998c148a2e7848aa95b1c4a4066d078_30.png)

![](img/0998c148a2e7848aa95b1c4a4066d078_31.png)

That code searches a string instance variable， my text。



![](img/0998c148a2e7848aa95b1c4a4066d078_33.png)

The code will copy， uses the methods dot length and dot index of we'll need to change these。



![](img/0998c148a2e7848aa95b1c4a4066d078_35.png)

The code we copy also uses dot substring to create the one character strings added to the array list of values that follow the key。

 We' replace dot substring also。

![](img/0998c148a2e7848aa95b1c4a4066d078_37.png)

![](img/0998c148a2e7848aa95b1c4a4066d078_38.png)

![](img/0998c148a2e7848aa95b1c4a4066d078_39.png)

These changes are necessary because my text changes from a string to a string array。

Replacing dot length and dot substring will be very simple。

 but we'll need to write a helper method to use in place of the string method dot index of。

Java doesn't supply the same type of general method for a search that returns an index in an array or an array list。

A rayless does have a dot contains method that returns a boolean and a method that returns the first or last index of a value。

 but not a method that starts search at a specific index like the string index of method does。

We'll write that as helper methods and have a working program。

