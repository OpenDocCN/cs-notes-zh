# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p154 34_04_03_一阶模型辅助函数.zh_en -BV18U411U729_p154-

![](img/deb3d0ef0f0147a7d0ef0ce0e5367aef_0.png)

Hi， we'll develop and test the code for Markov word 1。 We'll copy the helper method。

 Get follows for Markov1。 We generally don't like to copy code， but you haven't learned yet。

 the right way to abstract this out to avoid duplication。

 You'll learn a better way than copying the code soon。

 Since my text is now an array of strings rather than an array willll need to make some changes。

 Some changes will be easy。 We'll need to change the string method dot length with parentheses to just dot length without the parentheses to find the number of strings in the array。

 My text We'll have harder changes。 too， since we'll need to replace the string dot index of method。

 We' the helper method to return the index of a search string key starting at a specified index in an array。

 Let's get started。 Hi， in this coding demo， we're gonna to look at the Markov word1 class that uses an order1 markov process。

 but with words rather than characters or letters to see how this works， I'm going to use。😊。



![](img/deb3d0ef0f0147a7d0ef0ce0e5367aef_2.png)

Our Markov runner class and create an object of type Markov runner on my object workbench。

And invoke the runmarkov method。 This is using an order one text。

 I'm going to use Confucius and see what kind of random text we have。



![](img/deb3d0ef0f0147a7d0ef0ce0e5367aef_4.png)

We've seen this before， and we can see here that it printed out， I'm using the mark of one class。

This is text that's a little difficult to understand because each letter predicts one letter that follows it。

 We're going to use the same code and the same ideas as you've already seen。

 but with words instead of letters， the way I'm going to do that is to modify the code in run Markov to use Markov word one rather than。

Markov one。There's Markov Word 1， Markov word 1。 Now I'm going to compile this code。

 it compiled with no syntax errors。I'm going to come to my object workbench。And make an object。

 I had to make a new one since I just recompiled it。

And now I'm going to use the runmarkov method again。With Confucius。

And I see that I get one random word of text rather than a 200 that I asked for。

 Notice I am using Markov word 1。 It prints the name of the class。 courtesy， We and children。

 I'd like to get 200 words rather than one。 Let's see where that code is letting me down。

In the Markov class。 So in Markov word 1。We've already seen in previous examples that the set training method is done for us。

 I'm using an array of strings rather than one string。I've written the get random text method。

And that works just as the method worked in Markov1 for letters。By calling get follows。

 And it's the get follows method that I'd like to look at。 Not surprisingly。

 this method returns an empty array list， since I haven't written it yet。

 I have to fill the follows array list with each word that follows my key。

 The way I'm going to start that is to take the code in Markov one for follows。

And copy and paste that into。The function that I'm writing now。

 copying and pasting is not really a great idea。But until we learn about abstract based classes in a future lesson。

 I don't have much choice。 So I'm going to come into my markov word1 class。

Make some space for this code that I just copied and paste it。Forgot one letter there。Now。

 if I try to compile this， it's likely not going to compile。

 cannotnot find symbol method length in my new version。My text variable is an array。

In the previous version with letters， it was a string。 Strings have a dot length method。

And arrays have simply a dot length。That's two places that I'm replacing the length method with the length field that's in the right class。

 When I compile this， cannot find symbol index of strings have an index of method that allows me to find the location of this key starting at a given position。

I'm going to have to replace the string method index of with my own helper method that's inside the class。

 We can see here that it has three parameters。 The array of strings we're searching for。

 the target we're searching。For in that array in the location。I'm going to simply replace。

My text do index of with the helper method。Index of my text。Now。

 my text is a parameter rather than being the object on which the index of method is invoked as it was with strings。

Cannot find method substring in strings to find a specific character。 I used substring and said。

 start here and take this many characters in my new model， because this is Markov1。

 I simply need to get。The text that starts at。Daart。Plus one， the reason I'm using start plus1。

Is that I have a one character look ahead。 So I just need the next character rather than the general code that I had here to make that clearer in case。

It's not quite clear enough。In a word one model， I'm using one word。To predict the next word。

 So since I found the word at index start， I take the word after that and add it to my follows array。

My class is compiled and there are no syntax errors if I now compile Markov Runner again。

And then make a new object。And invoke the run markov method。Unconfucius。I still get one word。

 a different word because it was random。 And the reason I get only one word is because although I've made my follows method work。

 at least compile， which gives me high confidence that's going to work。 my index of method。

 which searches through the array of string words for this particular target starting at a given position。



![](img/deb3d0ef0f0147a7d0ef0ce0e5367aef_6.png)

Simply returns negative one， meaning the string wasn't found。

 So I need to search for every string and return the location。I'm going to start。

My search at this location given by the parameter start。I'm going to search through all the words。

Which I use the length of the array to tell me when the end is。

 and I'm going to increment my variable each time。If the word I'm looking for is my target。

 I've found it。If words subK is equal to now， with equal to with strings。

 I need to remember to use dot equals。 If that's equal to my target。

I'm simply going to return the index at which I found it。Which is K。So I've taken this for loop。

 which is a standard loop over all the variables。The values inside words， starting at start。

And going through the length of the array。 If I find the word I'm looking for。

 which means words sub K dot equals target， I return the index because this returns the index of the first occurrence of target that occurs on or after location start。

 If I make it all the way through this for loop without finding it， the loop exits。

 and I'll return negative one， meaning it wasn't found。This code compiles。

I'll now compile Markov Runner。I'll create a Markov runner object。On the object workbench。

I'll invoke its run Markov method with Confucius。And now I have 200 random words。

 Vasals are Jada's past。 The master said， when the madhead of the balance of Kai told how about the project。

 this is nonsensical text， but each word。Is real because I chose words at random。

 as they say in the House of Lo， Vex is for five seeds。Enjoy the code。

