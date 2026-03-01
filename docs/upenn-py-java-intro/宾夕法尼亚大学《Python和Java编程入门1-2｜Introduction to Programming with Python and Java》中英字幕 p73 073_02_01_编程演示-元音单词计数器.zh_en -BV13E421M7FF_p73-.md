# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p73 073_02_01_编程演示-元音单词计数器.zh_en -BV13E421M7FF_p73-

Write a program that counts the number of vowels in a string。



![](img/9689a3be56cbdfe762612779f6869ee4_1.png)

And counts the number of words in a sentence。Let's start by creating a vowel counter function。

D F vowel。😔，Counter。😔，For a given string。Counts the number of vowels in given string。

I'm going to initialize a count variable。Vel count equals 0。

And then we're going to iterate over given string。For each character in the string。

 check if that character is a vowel。 So if the character is in the string， A E。 I O U。

 if it's one of them， it's a vowel。Rowul count。😔，Incremented。

So here we're check if character is a vowel increment vowel count。Return， vowel。

 count from the function。Now we're going to define a main function that calls and runs the vowel counter function within a loop。

 and then we'll run our program。D E F main is our main function。I'm going to create a loop。

While one equals  one。 So this is an infinite loop。 While one is equal to one， which is always true。

 Run the loop。Get an input string。Enter a string。Check the input。 If it's negative  one。

 break out of the loop and exit the program。 Otherwise， count the vowels in that string。 So if。

The input string。Is equal to negative1。 This allows the user to exit the loop。Will break。

 This break will break out of this while loop。 Otherwise， call vowel counter。With the input string。

And print the results。 the number of vowels in that string。Print our counter with the input string。

Vowels in。Input string。To run our main function， we're going to check the value of the special name variable。

So if underscore， underscore， name， underscore， underscore is equal to underscore， underscore， main。

 underscore， underscore。Then， run， mean。To execute main function。Enter a string。Hello。😔。

2 vowels and hello。N， E A neat。2 os in meat。Okay。1 vowel。 in O， negative  one。Exitts the loop。

 and were done。Now， let's create a word counter function to count the number of words in a given sentence。

So， T EF。Word。Counter。For a given sentence。Counts the number of words in given sentence。

We're going to be using single spaces for counting the number of words in a sentence。

 We're going to look for spaces。 So let's strip the white space from the beginning and end of the given sentence。

Sentence equals。Sentence dot strip。Removes white space from。Beginning and end of。Sentence。Now。

 we're going to count the spaces in the sentence。 So let's start with a space count。

Space count equals 0。Let's iterate over each character in the sentence and see if it's a space。

For each character。In sentence。Check if it's a space。 So if char is in the string， empty string。

It's a space。Space count plus equal to one。I。Check if character is single space。

The word count will be the number of spaces plus one word count。Eals space count plus  one。So， then。

Return。😔，The word count。Now， let's add the word counter function call to the main function。

So instead of vowel counter。Let's call。😔，Word counter。For a given input string。Words in。😔，Input。

String。To runun our program。Interesting， how are you。3 words。 And how are you。I am fine，3 words。

 and I am fine。That is great to hear。5 words in。 That is great to hear Ne one to exit。Note。

 both the vowel counter function and the word counter function have a similar code block here in the vowel counter function。

 we initialize a count。Iterate over a string。 Look for a particular character。

 and then increment the count。In word counter， we initialize a count。



![](img/9689a3be56cbdfe762612779f6869ee4_3.png)

Iterate over a string。 In this case， a sentence。 Look for a particular character。And then。

 increment count。So let's create a separate function that does just that。

 This is known as refactoring the code。Let's create a count instance of string function。D F count。

Instance of S TR for a given string 1。And string 2。Counts characters in string 1 that are also in。

String 2。😔，Initialize account。For each character。In string 1。Check if it's in string 2。

 So for each character in string 1。If a character is in。String 2， increment the count。And then。

 return。The count。Now we can use the count instance of string function in our other functions。

So in our word counter。Change this。

![](img/9689a3be56cbdfe762612779f6869ee4_5.png)

that。As our sentence， we're going to get the number of spaces。Provided to us by count instance of。

String function。By giving it the sentence and the character that I want to look for。

That'll be the number of spaces。Number of words。Will be the number of spaces plus one。

Pction F5 enter a string。 How are you？3 words。 And how are you， I am fine。Few words。 And I am fine。

That is great to hear。5 words。 And that is great to hear And negative one to exit。

And we can also use that function in our vowel counter function。 So count instance of string。



![](img/9689a3be56cbdfe762612779f6869ee4_7.png)

So here vowel counts， vowel count equals count instance of string。



![](img/9689a3be56cbdfe762612779f6869ee4_9.png)

For the given string。Looking for A E I O U。That a survival account。Can run this here。

Comment that out。😔，Function F 5 enter a string。Hello。😔，2 vows。 and hello。Nat。2 vowels in neat。Okay。😔。

1 vowel。 And okay。Negative one to exit。And we' refactored our code。



![](img/9689a3be56cbdfe762612779f6869ee4_11.png)