# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p156 36_04_06_WordGram类实现.zh_en -BV18U411U729_p156-

![](img/52e33d70cb34dff15b11aa4a2ec6e30f_0.png)

Yeah。As part of creating the design of a class， you'll typically want to think about how the class is used。

 This is often called generating use cases and can be done for a class as well as for our program。

 We'll think about how a word gram object will be used in our Markov programs。

 We have some experience to build on here。 We'll create a word gram from an array of strings。

This is an analog of creating a string from in characters as when substring is used。

 We'll need to add a new string to the end of a word gram。

 This is an analog of adding a following character to make a new key when generating random text。

We're ready to summarize our initial design of word gram。 The state will be an array of strings。

 We'll store this in an instance variable， just as my text was a string in the character Markov programs。

 We'll look at simple behavior first。 We'll need a git method to obtain the length of a word gram just as string has a dot length。

 This is called a git method because it simply gets a value。

 We'll need a method that's an analog of dot cha at for strings。

 but to get the word at a specific index。 We'll want programmers to be able to use word gram like other classes。

 This means we'll need a dot2 string method for printing and other uses。

 and we'll need a dot equals method for finding follows， as we'll see soon。😊。



![](img/52e33d70cb34dff15b11aa4a2ec6e30f_2.png)

We might think about a dot compare to method and having the word Gram class implement the comparable interface that might make it general。

 but in our analysis of how word G would be used， we didn't come up with sorting。

 We won't design a feature that isn't going to be used。 We can add features later as needed。

Let's design the constructor for word gram Conors initialize the state you can see the code for the constructor here In this case the state is an array of strings we've named my words the strings in this array are copied from the source array passed as a parameter to the constructor the number of strings to copy is another parameter to the constructor as is the starting index of where to copy the strings from the method system array copy copies values from a source array to a destination array In this case。

 the destination is instance variable my words。We'll look at the code for simple behavior in Word G。

 these methods are direct analogs of string methods。

Method dot word at returns the string at a specified index。

 just as dot cha at returns the char at a specified index in a string。If the index isn't valid。

 either too low or too high， the method throws an exception You've likely had such exceptions when you've made a bad index in accessing array or array lists or string values here our code is like other classes in throwing an exception you'll learn more about exceptions if you continue to study Java。

For now， we want our class to act like other classes。The number of words is returned by dot length。

 just as the number of characters is returned by dot length in the string class。

 We've got two more methods so that word gra behaves well with other classes。

 just as our dot word app method acted like related classes and throwing an exception for a bad index。

 we need these methods， because programmers expect them。 we' create a dot2 string method。

 as you've seen with other examples， This will help with printing word gras。

 either in output or as debugging help。 We'll also need dot2 string to append values to a string builder object in the git random text method。

 we'll create a dot equals method2， This will be important in determining when one word gra object is equal to another in writing the git follows helper method。

 Word gra objects are equal if their links are equal。

 and if the strings that corresponding indexds are equal to。



![](img/52e33d70cb34dff15b11aa4a2ec6e30f_4.png)

We'll need to use dot equals rather than equals equals to check whether two strings are equal。

We'll look briefly at how code changes in moving from characters to words once the word gra class is completed。

 you'll do more on your own and in later lessons。

![](img/52e33d70cb34dff15b11aa4a2ec6e30f_6.png)

You'll need to generate random text and the get random text method in the character Markov to class。

 random text would be two character sequences like T H and E that appear in the training text。

 These are obtained using the dot substr method in the word Markov to class。

 random text is sequences like how long and no such。

 these sequences are formed by creating a new word gra object using the same arguments as in the character class。

 My text index and my order。 happy programming。